# HDB Resale Price Analysis: Impact of 'Good' School 

## Project Overview
This project examines whether proximity to “good” primary schools affects HDB resale prices in Singapore. Using regression and spatial models, we isolate the impact of school proximity while controlling for housing and location characteristics.

## Setting up the repository
1. Run `python -m venv venv` to create a virtual environment  
2. Run `source venv/bin/activate` to activate it  
3. Run `pip install -r requirements.txt` to install dependencies  

---

## Project Workflow

### 1. School Data Cleaning
Navigate to `data_cleaning_school/` and run:
- `data cleaning.ipynb`

This step prepares raw school datasets such as:
- general school information  
- co-curricular activities (CCA) 
- subjects offered  
- distinctive programmes
- affiliations  
- demand scores  

---

### 2. School Scoring
Navigate to `school_scoring/` and run:
- `school_scoring.ipynb`

This step:
- performs PCA on school features  
- constructs a school quality index  
- generates tiered school classifications  

Outputs:
- `schools_tiered_withscores.csv`  
- visualisations (eg. PCA variance, PC1 loadings)

---

### 3. HDB Data Cleaning, Feature Engineering & School Merge
Navigate to `data_cleaning_hdb/` and run:

- `resale_price_feature_eng.ipynb`
- distance-related notebooks:
  - `walking_distance_mrt.ipynb`
  - `walking_distance_mall.ipynb`
  - `walking_distance_hawker.ipynb`
  - `walking_distance_bus_stop.ipynb`
  - `euclidian_distance_cbd.ipynb`

This step:
- cleans HDB resale data  
- performs feature engineering
- generates distance-based features to amenities  
- merges school features with HDB transactions
- creates proximity indicators (eg. within 1km/2km)

---

### 4. Exploratory Data Analysis
Run:
- `models/eda.ipynb`

This step:
- examines distributions of key variables (eg. resale price, school distance)
- analyses school proximity patterns (1km/2km)
- explores spatial variation across towns
- evaluates correlations between variables

---

### 5. Modelling
Navigate to `models/` and run:

- `data_prep.ipynb` → prepares model-ready datasets
- `hedonic_pricing_ols.ipynb` → regression analysis (OLS)  
- `hdb_spatial_models.ipynb` → spatial econometric analysis
- `RD copy.ipynb` → regression discontinuity (RD) analysis  

This step:
- estimates the effect of school proximity on resale prices  
- compares results across different model specifications  

---

## Data Availability
Processed datasets are not included in this repository.

To reproduce the results:
- run the data cleaning and feature engineering notebooks in sequence  
- intermediate datasets will be generated during execution  

---

## Key Findings (Summary)
- Proximity to good schools has a small but positive effect on resale prices  
- At 1km, the effect is largely explained by neighbourhood characteristics  
- At 2km, a small premium (~1–2%) remains after controls  
- Overall, school proximity is not the main driver of resale prices  

---
