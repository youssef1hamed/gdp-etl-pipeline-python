# Global GDP ETL Pipeline 🌍

## 📌 Project Overview
This project was developed to assist an international firm in identifying expansion opportunities by automating the extraction and analysis of global GDP data. The pipeline extracts economic data from the IMF via Wikipedia, transforms it from Millions to Billions, and loads it into both a CSV file and a SQL database for querying.

## 🛠️ Objectives
This script performs the following tasks:
* **Extraction**: Web scraping data using `BeautifulSoup` from an archived Wikipedia URL.
* **Transformation**: Converting GDP values from 'Million USD' to 'Billion USD' (rounded to 2 decimal places).
* **Loading**: Storing the cleaned data in `Countries_by_GDP.csv` and a SQLite database named `World_Economies.db`.
* **Querying**: Running SQL queries to filter countries with a GDP exceeding 100 Billion USD.
* **Logging**: Creating a timestamped log file (`etl_project_log.txt`) to track the pipeline's progress.

## 🏗️ The ETL Architecture


### 1. Extract
The script identifies the correct table by searching for the "Country/Territory" header. It uses defensive logic to ensure it only processes rows containing valid hyperlinks and non-null IMF estimates.

### 2. Transform
Using `NumPy` and `Pandas`, the "GDP_USD_millions" column is cleaned (removing commas), converted to float, divided by 1000, and renamed to "GDP_USD_billions".

### 3. Load
The final data is persisted in two formats:
* **Relational**: A SQLite table named `Countries_by_GDP`.
* **Flat File**: A CSV file for easy sharing and portability.

## 🚀 How to Run
1. **Clone the repository**:
   ```bash
   git clone [https://github.com/youssef1hamed/gdp-etl-pipeline-python.git](https://github.com/youssef1hamed/gdp-etl-pipeline-python.git)
