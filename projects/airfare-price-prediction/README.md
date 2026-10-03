# Airfare Price Prediction & Business Analytics

## Project Overview

This project analyzes airline fare data to identify the factors associated with airfare levels and build a predictive model that can support route-level pricing analysis.

The analysis combines exploratory data analysis, regression modeling, model selection, validation, and scenario analysis to translate statistical results into practical business insights.

## Key Results

| Metric                    |                        Result |
| ------------------------- | ----------------------------: |
| Final model               | BIC-selected regression model |
| Predictors                |                             9 |
| Adjusted R²               |                         0.766 |
| Validation RMSE           |                        $32.82 |
| Top 10% lift              |                         1.81× |
| Baseline prospective fare |                       $182.24 |
| Southwest scenario        |                       $137.95 |
| Model-adjusted difference |                       -$44.29 |
| Pre-operation model RMSE  |                        $33.94 |

## Business Problem

Airline pricing varies across routes and operating conditions. The objective was to determine which measurable factors are most associated with fare levels and assess whether the resulting model can provide useful fare estimates for prospective route scenarios.

## Analytical Approach

* Explored relationships between airfare, distance, passenger demand, market characteristics, and operating conditions.
* Compared numerical and categorical drivers of average fares.
* Built multiple linear regression models.
* Used AIC-based stepwise selection and exhaustive subset selection to compare model complexity and fit.
* Selected a more compact BIC model with 9 predictors.
* Validated the model using a held-out validation set.
* Evaluated model usefulness using lift analysis.
* Performed prospective route and competitor scenario analysis.
* Built a pre-operation model excluding passenger volume to test how early fare estimates can be generated.

## Key Business Insights

### 1. Route and operating characteristics matter

Fare levels are associated with a combination of route distance, market characteristics, vacation status, Southwest presence, and airport operating conditions.

Distance showed a positive relationship with fare, while several categorical operating factors were associated with meaningful differences in average fares.

### 2. The model provides useful ranking capability

The final model achieved a validation RMSE of approximately **$32.82**.

More importantly for prioritization, the highest predicted-fare 10% of validation observations had an average fare approximately **1.81× the overall validation average**, indicating useful ranking power for identifying relatively high-fare opportunities.

### 3. Scenario analysis supports competitive benchmarking

For a prospective route with fixed market and operating characteristics, the model estimated:

* **Baseline:** $182.24
* **Southwest scenario:** $137.95
* **Model-adjusted difference:** -$44.29

This difference represents a **model-adjusted association**, not a causal estimate.

### 4. Earlier forecasting is possible

A pre-operation model excluding passenger volume produced a validation RMSE of **$33.94**, compared with **$32.82** for the final model.

This suggests that useful fare estimates can be generated before passenger-volume information is available, although with some loss in predictive accuracy.

## Validation & Model Selection

The analysis used a 70/30 training-validation split.

The final BIC-selected model retained 9 predictors and provided a more compact specification than the larger candidate models. Its validation performance was only modestly worse than the stepwise AIC model while using fewer predictors.

This trade-off favors a model that is easier to interpret and communicate to business stakeholders.

## Limitations

* The analysis identifies statistical associations rather than causal effects.
* The dataset represents a historical snapshot and may not reflect current airline pricing behavior.
* Validation performance depends on the available sample and split.
* Additional time-based, competitive, and market-level variables could improve future models.
* Prospective scenario estimates should be treated as analytical benchmarks rather than guaranteed market prices.

## Tools

**Python · Pandas · NumPy · Matplotlib · Scikit-learn · Statsmodels · Kaggle**

## Project Outputs

The repository contains the supporting analysis, model outputs, and visualizations used to communicate the findings.

The full interactive analysis is available through the accompanying Kaggle notebook.
