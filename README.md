# Project Description
Banks have trouble managing the thousands of complaints they get every day. They usually just use basic computer searches that look for simple keywords, which often miss the real problems. Instead, this system reads the complaints just like a person would to find the actual issues such as long delays, website bugs, or legal concerns. It then gathers these complaints together and writes a short, simple summary for the bank so they know exactly what needs to be fixed.

# Dataset
This dataset is a collection of over 6,000 customer complaints about Bank of America’s financial products and services. It contains records of consumer complaints filed against Bank of America, providing insights into the issues faced by customers regarding their financial products and services.

## What is the source of this information?
The data comes from the *Consumer Complaint Database* maintained by the **Consumer Financial Protection Bureau** (CFPB).

It is a public databse where you can find real complaints that people have submitted about financial products and services, like mortgages, credit cards, and bank accounts.

## The URL
This page allows you to search, filter, and track trends in consumer complaints. The **List** tab in the CFPB is the view foe browsing individual complaints one by one.
[https://www.consumerfinance.gov/data-research/consumer-complaints/search/?dateRange=3y&date_received_max=2026-04-22&date_received_min=2023-04-22&page=1&searchField=all&size=25&sort=created_date_desc&tab=List]


**Filtered Search Query**
- **company=BANK+OF+AMERICA%2C+NATIONAL+ASSOCIATION**: This limits my entire dataset to only complaints filed against Bank of America.
- **product=Credit+card+or+prepaid+card & product=Mortgage**: I have restricted the scope to these two specific types of financial products.
- **date_received_min=2021-01-01 & date_received_max=2026-04-22**: I am covering almost 5 years of data from Bank of America to analyze trends over time.
- **has_narrative=true**: By setting this to true, I am making sure that every 6,197 records includes the actual, written description from the consumer instead of thousands of records that only show "Checkboxes" (like the product or company name) but lack the actual stories needed for your NLP model to analyze.
- **size=6197**: this is the filtered size. This tells the database to provide all the data that matches my filters in a single batch.
- **format=csv**: this is my export format.
- **no_aggs=true**: This tells the system not to provide extra "summary" calculations (like counts of complaints per state). I am looking for the raw, individual complaint data instead.


**Downloadable filtered link**
Link to complaint search result
[https://www.consumerfinance.gov/data-research/consumer-complaints/search/api/v1/?company=BANK%20OF%20AMERICA%2C%20NATIONAL%20ASSOCIATION&date_received_max=2026-04-22&date_received_min=2021-01-01&field=all&format=csv&has_narrative=true&no_aggs=true&product=Credit%20card%20or%20prepaid%20card&product=Mortgage&size=6197]

## Column Description
The dataset has overall 6,197 rows and 18 columns.

**Column1**
- Name: Date received
- Data Type: object
- Description: The date the complaint was received by the agency. 

**Column2**
- Name: Product
- Data Type: object
- Description: The type of financial product or service involved (e.g., Credit card, Mortgage).

**Column3**
- Name: Sub-product
- Data Type: object
- Description: The specific sub-type of the financial product.

**Column4**
- Name: Issue
- Data Type: object
- Description: The primary category of the complaint.

**Column5**
- Name: Sub-issue
- Data Type: object
- Description: A more detailed classification of the issue.

**Column6**
- Name: Consumer complaint narrative
- Data Type: object
- Description: A text description provided by the consumer explaining their issue.

**Column7**
- Name: Company public response
- Data Type: object
- Description: The company's response to the complaint.

**Column8**
- Name: Company
- Data Type: object
- Description: The name of the company the complaint is against (in this case Bank of America).
	
**Column9**
- Name: State
- Data Type: object
- Description: The state where the consumer resides.

**Column10**
- Name: ZIP code
- Data Type: object
- Description: The ZIP code of the consumer's location.

**Column11**
- Name: Tags
- Data Type: object
- Description: Categorical tags (e.g., "Older American," "Servicemember").

**Column12**
- Name: Consumer consent provided?
- Data Type: object
- Description: Whether the consumer consented to share their narrative.

**Column13**
- Name: Submitted via
- Data Type: object
- Description: The method used to submit the complaint (e.g., Web, Phone).

**Column14**
- Name: Date sent to company
- Data Type: object
- Description: The date the complaint was forwarded to the company.
 
**Column15**
- Name: Company response to consumer
- Data Type: object
- Description: The final outcome or status of the complaint resolution.

**Column16**
- Name: Timely response?
- Data Type: object
- Description: Whether the company responded within the required timeframe.

**Column17**
- Name: Consumer disputed?
- Data Type: float64
- Description: Indicates if the consumer disputed the company's response (currently contains only missing values).

**Column18**
- Name: Complaint ID
- Data Type: int64
- Description: A unique identifier for each complaint.

## What you need to know about the health and reliability of this information
**Missing Data**:

- The *Consumer disputed?* column number 17 is entirely empty and contains no data.
- Some columns such as *Sub-issue* and *Tags* have varying degrees of missing values, reflecting that these fields are not applicable to every complaint.
- The *Consumer complaint narrative* column contains unstructured text data, which can be useful for natural language processing (NLP) and sentiment analysis to identify common themes in consumer dissatisfaction.

