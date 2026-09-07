# End-to-end-ETL-Extract-Transform-Load-pipelines

Largest Banks ETL Pipeline

An automated ETL (Extract, Transform, Load) pipeline built in Python that compiles the top 10 largest banks in the world by market capitalization, converts the figures into multiple currencies, and stores the results in both CSV and SQLite database formats — designed to be re-run automatically every financial quarter.


Project Scenario
Built as a data engineer would for a research organization: a repeatable script that scrapes bank market cap data, transforms it using live exchange rates, and produces a report-ready dataset each quarter with zero manual work.



Pipeline Overview\
Extract	Scrapes the "By market capitalization" table from an archived Wikipedia snapshot using requests + BeautifulSoup, producing Name and MC_USD_Billion columns.


Transform	Reads exchange rate data (exchange_rate.csv) and adds MC_GBP_Billion, MC_EUR_Billion, and MC_INR_Billion columns, each rounded to 2 decimal places.


Load	Saves the final table to Largest_banks_data.csv and to a Largest_banks table inside a SQLite database (Banks.db).


Query	Runs SQL queries against the database: full table dump, average market cap in GBP, and the top 5 bank names.





Project Parameters


Parameter	Value

Code name:	banks_project.py

Data source:	Archived Wikipedia "List of largest banks" page

Exchange rate: source	CSV file (Currency, Rate columns)

Extracted columns:	Name, MC_USD_Billion

Final columns:	Name, MC_USD_Billion, MC_GBP_Billion, MC_EUR_Billion, MC_INR_Billion

Output CSV: ./Largest_banks_data.csv

Database:	Banks.db

Table name:	Largest_banks

Log file:	code_log.txt



Tech Stack & Skills

Language: Python

Libraries: requests, beautifulsoup4, pandas, numpy, sqlite3


Skills demonstrated: Web Scraping, REST APIs, ETL pipeline design, Data Transformation, Data Wrangling, Data Pipelines, Database Management, SQL querying, Programming Principles, Maintainability (structured logging), HTML parsing



How to Run

Install dependencies:
   pip install requests beautifulsoup4 pandas numpy

Make sure exchange_rate.csv is in the same folder as the script.

Run the pipeline:
   python banks_project.py
The script will print the extracted and transformed data, save Largest_banks_data.csv, create/update Banks.db, run the sample queries, and log every stage to code_log.txt.
