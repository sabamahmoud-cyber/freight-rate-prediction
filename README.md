# Freight Rate Prediction

Machine learning solution for predicting freight load rates using historical shipment data.

## Project Overview

The objective of this project is to predict `posted_rate` for future freight loads using historical load characteristics such as route, distance, equipment type, weight, market information, and date.

The development dataset was explored, cleaned, and used to compare multiple regression models.

A chronological validation strategy was used because the final prediction task involves forecasting future loads.

## Models Evaluated

- Linear Regression
- Random Forest Regressor
- Linear Regression with engineered interaction features

Linear Regression was selected as the final model because it achieved the best out-of-time validation performance and showed the smallest gap between training and validation results.

## Validation Strategy

The labeled development data covers January through October 2025.

To simulate future prediction:

- January–September 2025 were used for training.
- October 2025 was used as the local validation period.

After model selection, the final Linear Regression model was retrained using the complete labeled development dataset.

## Local Validation Results

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | 141.87 | 651.27 | 0.82 |
| Random Forest | 243.59 | 759.31 | 0.75 |
| Linear Regression + Interactions | 153.26 | 655.11 | 0.82 |

## Project Structure

```text
freight-rate-prediction/
├── Machine_Learning_Assessment.ipynb
├── requirements.txt
├── README.md
└── validation_predictions.csv
