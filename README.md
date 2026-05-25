# NYC Taxi Trip Analysis – PySpark ML Pipeline

End-to-end machine learning pipeline analyzing tens of millions of NYC taxi 
trips using PySpark in a distributed computing environment.

## Project Overview

Built as part of the Big Data Systems course at Kristiania University College. 
The project demonstrates handling of large-scale real-world data — from raw 
ingestion and cleaning through feature engineering to ML model training and 
evaluation across two taxi datasets (Yellow and Green, 2020–2024).

## What This Project Covers

- Automated download of NYC TLC trip data (2020–2024) via HTTP requests
- Data cleaning and validation using modular PySpark functions based on 
  official TLC 2025 metadata
- Medallion Architecture (Bronze → Silver → Gold) for structured pipeline design
- Exploratory Data Analysis (EDA) using PySpark SQL and DataFrame API
- Feature engineering: time-based features, trip duration, distance bins, 
  one-hot encoding
- ML model training and evaluation with Spark ML:
  - Linear Regression (baseline)
  - Random Forest Regressor
  - Gradient Boosted Trees (GBT)
- Model evaluation using RMSE, MAE, and R²
- Actual vs. predicted visualizations with Seaborn

## Key Results

| Dataset | Model | RMSE | MAE | R² |
|---------|-------|------|-----|----|
| Green | GBT | ~6.28 | ~2.99 | ~0.82 |
| Green | Random Forest | ~6.52 | ~3.12 | ~0.80 |
| Green | Linear Regression | baseline | — | ~0.75 |
| Yellow | Linear Regression | ~5.65 | ~3.33 | ~0.86 |

## Tech Stack

| Component | Version |
|-----------|---------|
| Python | 3.10.0 |
| PySpark | 4.0.1 |
| JDK | 17 |
| Hadoop Client | 3.3.5 |
| SQLite JDBC | 3.36.0.3 |

```
BDS4100_PROJECT/
├── Green_Clean_Chunks/
├── Yellow_Clean_Chunks/
├── NYC_Taxi_Trip_Data_CSV/
├── NYC_Taxi_Trip_Data_Parquet/
├── nyc_taxi_pyspark_ml_pipeline.ipynb
├── nyc_green_taxi.db
├── nyc_yellow_taxi.db
├── sqlite-jdbc-3.36.0.3.jar
└── taxi_zone_lookup.csv
```

## How to Run

Only two external files are needed to re-run from scratch:
- taxi_zone_lookup.csv (included in repository)
- sqlite-jdbc-3.36.0.3.jar (download separately from Maven Repository)

All other files (Parquet, CSV, cleaned chunks, SQLite DBs) are generated 
automatically during execution. All results, plots, and outputs are already 
present in the notebook.

## Grade
A
