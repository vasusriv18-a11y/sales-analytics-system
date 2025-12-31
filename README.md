# Sales Analytics System

Complete **Sales Data Processing & API Enrichment Pipeline** with comprehensive analytics and reporting.

## Project Structure
```
sales-analytics/
├── sales_data.csv              \# Input sales transactions (95 records)
├── products.json               \# DummyJSON API cache (194 products)
├── file_handler_py.py          \# File I/O \& data parsing
├── data_processor_py.py        \# Sales analytics functions
├── api_handler_py.py           \# DummyJSON API integration
├── main.py                     \# Main execution workflow
├── data/                       \# Output: enriched_sales_data.txt
└── output/                     \# Output: sales_report.txt

```



## Quick Start

### 1. Prerequisites


# Python 3.8+

pip install pandas requests


### 2. Place Files
Ensure all 6 files are in the same directory:

sales_data.csv
products.json
file_handler_py.py
data_processor_py.py
api_handler_py.py
main.py  \# (create from provided code)


### 3. Run Complete Pipeline

python main.py


## Expected Output

===========================================
SALES ANALYTICS SYSTEM
===========================================

[1/10] Reading sales data...
✓ Successfully read 95 transactions

[2/10] Parsing and cleaning data...
✓ Parsed 95 records

[3/10] Filter Options Available:
Regions: North, South, East, West
Amount Range: ₹500 - ₹90,000

[4/10] Validating transactions...
✓ Valid: 92 | Invalid: 3

[5/10] Analyzing sales data...
✓ Analysis complete

[6/10] Fetching product data from API...
✓ Fetched 194 products

[7/10] Enriching sales data...
✓ Enriched 85/92 transactions (92.4%)

[8/10] Saving enriched data...
✓ Saved to: data/enriched_sales_data.txt

[9/10] Generating report...
✓ Report saved to: output/sales_report.txt

[10/10] Process Complete!


##  Generated Files

### `data/enriched_sales_data.txt`


TransactionID|Date|ProductID|ProductName|Quantity|UnitPrice|CustomerID|Region|API_Category|API_Brand|API_Rating|API_Match
T001|2024-12-01|P1|Laptop|2|45000.0|C001|North|beauty|Essence|2.56|True


### `output/sales_report.txt`


SALES ANALYTICS REPORT
==================================================

EXECUTIVE SUMMARY
--------------------
Total Valid Transactions: 92
Total Revenue: ₹1,250,000.00

KEY INSIGHTS
---------------
Peak Sales Day: 2024-12-15 (₹185,000.00)
Top Region: North (42.3%)
Enrichment Success: 92.4%


## Module Breakdown

| Module | Purpose | Key Functions |
|--------|---------|---------------|
| `file_handler_py.py` | File I/O | `read_sales_data()`, `parse_transactions()`, `validate_and_filter()` |
| `data_processor_py.py` | Analytics | `calculate_total_revenue()`, `top_selling_products()`, `daily_sales_trend()` |
| `api_handler_py.py` | API | `fetch_all_products()`, `enrich_sales_data()`, `create_product_mapping()` |
| `main.py` | Orchestration | Complete 10-step workflow |

## Data Flow


sales_data.csv (95 records)
↓ [1-2] Parse \& Validate
92 Valid Transactions
↓ [3-5] Analytics
Top Products, Revenue, Trends
↓ [6-7] API Enrichment
194 Products → 92.4% Match Rate
↓ [8-9] Save \& Report
enriched_sales_data.txt + sales_report.txt


## Customization Options

### Filter Data Interactively
**Modify `main.py` line 85-90:**

choice = input("Do you want to filter data? (y/n): ").lower()
if choice == 'y':
region = input("Enter region (North/South/East/West): ")
\# Apply filters via validate_and_filter()


### Custom Output Paths

save_enriched_data(enriched_data, 'custom/enriched.txt')
generate_report(..., 'custom/report.txt')


## Troubleshooting

| Issue | Solution |
|-------|----------|
| `ModuleNotFoundError` | Ensure all `.py` files in same directory |
| `FileNotFoundError` | Place `sales_data.csv` in project root |
| `UnicodeDecodeError` | File handler auto-tries UTF-8, latin-1, cp1252 |
| `API Failure` | Falls back gracefully, continues with cached `products.json` |
| `No pandas` | `pip install pandas requests` |

## Sample Insights Generated


Top 5 Products:

1. Laptop Premium: 25 units (₹1,200,000)
2. Wireless Mouse: 42 units (₹85,000)
3. USB Cable: 38 units (₹12,500)

Peak Day: 2024-12-15 (12 transactions, ₹185,000)
Region Split: North(42%), South(28%), East(20%), West(10%)

## Dependencies
- **Python**: 3.8+
- **Libraries**: `pandas`, `requests`
- **API**: DummyJSON (public, no auth)
- **Files**: 95 sales records, 194 product catalog


