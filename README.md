# 🏦 ETL Project: Acquiring and Processing Information on the World's Largest Banks

This project demonstrates an **ETL (Extract, Transform, Load)** pipeline built in Python.  
It extracts the list of the top 10 largest banks in the world by market capitalization from **Wikipedia**, transforms the data into multiple currencies, and loads it into both **CSV** and **SQLite database** formats.

---

## 🚀 Features
- Web scraping using **BeautifulSoup**
- Data transformation using **Pandas and NumPy**
- Currency conversion using an external CSV file
- Automated logging for each ETL stage
- Data storage in CSV and SQLite database formats

---

## 🧩 Tools & Libraries Used
- Python 3.11
- Pandas
- BeautifulSoup (bs4)
- NumPy
- SQLite3
- Requests
- LXML

---

## ⚙️ Workflow
1. **Extract:** Scrape the top 10 largest banks’ data from Wikipedia.
2. **Transform:** Convert market capitalization from USD to GBP, EUR, and INR using exchange rate data.
3. **Load:** Save the transformed data into:
   - A local CSV file (`Largest_banks_data.csv`)
   - A SQLite database table (`Banks.db` → `Largest_banks`)

---

## 🧠 Key Functions
| Function | Description |
|-----------|--------------|
| `log_progress(message)` | Logs progress messages to `code_log.txt`. |
| `extract(url, table_attribs)` | Extracts data from the Wikipedia page. |
| `transform(df, csv_path)` | Adds currency conversion columns. |
| `load_to_csv(df, output_path)` | Saves final data to CSV file. |
| `load_to_db(df, sql_connection, table_name)` | Loads data into SQLite database. |
| `run_query(query, sql_connection)` | Executes SQL queries on the database. |

---

## 📊 Example Queries
```sql
SELECT * FROM Largest_banks;
SELECT AVG(MC_GBP_Billion) FROM Largest_banks;
SELECT Name FROM Largest_banks LIMIT 5;
