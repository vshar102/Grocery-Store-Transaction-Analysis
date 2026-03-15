# Grocery Store Transaction Analysis

## Overview
In the bustling world of retail, understanding consumer preferences and shopping habits is pivotal for business optimization. This repository contains an R-based data analysis project aimed at uncovering hidden patterns in consumer behavior using transactional data from two 24-hour grocery stores.

The goal of this analysis is multifaceted:
- **Optimizing Store Layouts:** By identifying patterns in product purchases.
- **Tailoring Marketing Strategies:** Understanding seasonal/weekly trends and shopping hours.
- **Managing Inventory:** Aligning stock levels with customer preferences.

As a retail data scientist for the grocery chain, this analysis leverages detailed transactional data to drive strategic decisions, ultimately enhancing the customer experience and boosting the store's performance.

## Dataset
The project analyzes two datasets, `grocery_data1.csv` and `grocery_data2.csv`, which contain detailed records of grocery transactions. The datasets originate from two different stores with unique date storage practices due to the diverse backgrounds of the store owners. 

Both datasets share the following schema:
- `CustomerID`: Unique identifier for each customer
- `DateRaw`: Raw date of the transaction
- `Time`: Time of the transaction
- `TransactionID`: Unique identifier for each transaction
- `ProductName`: Name of the product purchased
- `PriceUSD`: Price of the product in US dollars
- `Quantity`: Number of the product purchased
- `PaymentMethod`: Payment type used for the transaction
- `Category`: Category of the product

## Technical Stack
- **Language**: R
- **Libraries**:
  - `dplyr`: For data manipulation and aggregation
  - `lubridate`: For date and time parsing and manipulation
  - `readr`: For fast and friendly data reading

## Key Analysis & Insights Generated
The analysis within the `notebook.ipynb` file performs several critical steps:
1. **Data Cleaning & Standardization**: 
   - Uses `lubridate` to parse the diverse date formats (`mdy` for Data 1, `dmy` for Data 2) across the two stores uniformly.
   - Merges the datasets from the two branches into a single analytical dataframe.
2. **Sales Metric Calculations**: 
   - Computes total sales value (`TotalSaleUSD`) for each transaction by multiplying `PriceUSD` by `Quantity`.
3. **Consumer Behavior Tracking**: 
   - Sorts and tracks distinct sequential purchases per customer to compute the `DaysSinceLastPurchase` for specific products (e.g., tracking the repurchase frequency of **Cornflakes** for specific customers).
4. **Temporal Sales Trends**:
   - Analyzes `WeeklyTotalSaleUSD` to find business consistency and sales variance (identifying the week with the smallest absolute deviation in sales value compared to the yearly mean).
   - Computes `HourlyTotalSaleUSD` showing that peak sales occur at **22:00 (10 PM)**.

## How to Run it
1. Ensure you have `R` installed alongside the packages: `dplyr`, `lubridate`, and `readr`.
2. Clone this repository to your local machine.
3. Keep the notebook (`notebook.ipynb`), image (`grocery_store.jpg`), and datasets (`grocery_data1.csv`, `grocery_data2.csv`) in the same directory.
4. Run the notebook in an environment that supports R Kernels (like Jupyter Notebook, JupyterLab, or DataCamp Workspaces).

## Potential Future Work
- Implementing predictive models for inventory stock-outs.
- Association Rule Mining (Market Basket Analysis) to find exactly which items are frequently bought together.
- Clustering customers into segments based on purchasing behaviour and value.
