🏠 Housing Price Prediction (PRCP-1020)
📌 Project Overview

This project focuses on predicting house prices using the Ames Housing Dataset.
The goal is not only to build an accurate prediction model but also to understand the key factors influencing house prices and provide actionable recommendations for buyers.

The project follows a complete machine learning pipeline:

Exploratory Data Analysis (EDA)

Data preprocessing & feature engineering

Model comparison

Hyperparameter tuning

Model interpretation using feature importance

🎯 Objectives

Exploratory Data Analysis

Understand data quality, distributions, correlations, skewness, missing values, and outliers.

Modeling & Interpretation

Build robust models to predict house prices.

Interpret feature importance to explain price drivers.

Actionable Recommendations

Translate model insights into practical guidance for home buyers.

📊 Dataset

Dataset: Ames Housing Dataset

Records: 1,460

Features: 80 (numerical + categorical)

Target Variable: SalePrice

Key Observations

The target variable SalePrice is highly right-skewed (skew ≈ 1.88).

Several numerical features contain outliers that can distort linear models.

Many categorical features have dominant categories.

Some columns contain significant missing values, requiring selective dropping or imputation.

🔍 Exploratory Data Analysis (EDA)
Target Variable Analysis

SalePrice violates linear model assumptions due to heavy skewness.

Tree-based ensemble models were preferred over purely linear approaches.

Feature Relationships

Strong positive correlation observed with:

OverallQual

GrLivArea

GarageCars

TotalBsmtSF

1stFlrSF

Multicollinearity exists among several numerical features, impacting interpretability.

Categorical Features

Certain categories (e.g., quality-related features) show a strong influence on sale price.

Boxplots revealed clear price separation across quality levels.

Missing Values

Columns with extremely high missing values were dropped.

Columns with manageable missingness were retained for modeling.

🛠️ Data Preprocessing & Feature Engineering

Dropped non-informative columns such as Id.

Ordinal categorical features were encoded using domain-informed ordering.

Nominal categorical features were encoded appropriately.

Final dataset used 73 features for modeling.

🤖 Modeling Approach
Models Evaluated

Multiple regression and ensemble models were trained and evaluated using:

RMSE

R² Score

Model Selection

Tree-based ensemble models outperformed linear models due to:

Skewed target distribution

Presence of outliers

Non-linear feature interactions

Best Model

XGBoost Regressor

Selected based on lowest RMSE

Further improved using hyperparameter tuning

Final model was saved for reuse

📈 Model Interpretation

Feature importance was extracted using Permutation Importance, which measures how much model performance drops when a feature is shuffled.

Top Price Drivers Identified

OverallQual

GrLivArea

TotalBsmtSF

BsmtFinSF1

GarageCars

1stFlrSF

2ndFlrSF

💡 Actionable Recommendations for Buyers

Prioritize overall quality (OverallQual)
Homes with better construction and material quality command significantly higher prices.

Choose larger above-ground living area (GrLivArea)
Larger usable living spaces strongly influence resale value.

Value finished basement space
Finished basements (TotalBsmtSF, BsmtFinSF1) add meaningful price premiums.

Prefer homes with larger garage capacity (GarageCars)
Garage space impacts price more than lot size or kitchen quality in this analysis.

Consider balanced floor layouts
Both first-floor and second-floor areas contribute moderately to price.

⚠️ Challenges Faced

Handling missing values across multiple feature types

Large number of categorical variables requiring careful ordinal encoding

Presence of outliers in numerical features

Multicollinearity affecting linear models

Highly skewed target distribution (log transform caused infinite values)

Building a robust preprocessing + modeling pipeline

Computational limitations and long training times

🧰 Tech Stack

Python

Pandas, NumPy

Matplotlib, Seaborn

Scikit-learn

XGBoost

🚀 How to Run

Open the notebook PRCP-1020-HousePricePred.ipynb

Ensure required libraries are installed

Run all cells sequentially
