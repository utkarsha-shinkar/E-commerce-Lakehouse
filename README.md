Ecommerce Lakehouse Pipeline (Databricks + PySpark + Delta Lake)
Overview
This project implements an end-to-end Databricks Lakehouse pipeline using Bronze → Silver → Gold architecture with SCD Type-2 dimensions, fact table modeling, data quality checks, orchestration, and job scheduling.

Tech Stack
PySpark
Delta Lake
Databricks
SQL
Architecture
Bronze → Silver → SCD2 Dimensions → Fact → Data Quality → Gold Aggregates

Folder Structure
ecommerce-lakehouse/
   ├── bronze/
   │   ├── 01_bronze_ingestion.py
   │   
   ├── silver/
   │   ├── 02_silver_transformations.py
   │   ├── 03_scd2_customers.py
   │   ├── 03_scd2_products.py
   │
   ├── gold/
   │   ├── 04_fact_sales.py
   │   ├── 05_data_quality_checks.py
   │   ├── 06_gold_sales_by_state.py
   │   ├── 06_gold_top_products.py
   │   ├── 06_gold_sales_trends.py
   │
   ├── utilities/
   │   ├── 07_delta_time_travel.py
   │
   └── orchestration/
       ├── 08_master_pipeline.py
Key Features
SCD Type-2 for Customers & Products
Analytics-ready Fact table
Gold business aggregations
Data quality validations
Delta Lake time travel & rollback
Notebook orchestration
Job scheduling ready
How to Run
Import repository into Databricks Repos
Run 08_master_pipeline
Schedule the master notebook as a Databricks Job
Gold Tables
gold_sales_by_state
gold_top_products
gold_daily_sales
Job Scheduling
The pipeline is executed using a Databricks Job that runs a single master notebook.

Job Details
Job Name: ecommerce_lakehouse_pipeline
Notebook: 08_master_pipeline
Cluster: Job cluster (auto-terminated)
Schedule: Daily at 01:00 AM IST
Reliability
Retries: 2
Retry Interval: 5 minutes
Job Timeout: 2 hours
This setup ensures automated, reliable, and production-ready execution.
