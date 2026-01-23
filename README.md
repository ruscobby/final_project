# Health Insurance Charges Determinats

## Objectives

To identify the key determinants of health insurance charges in the US

Evaluate predictive models to determine health insurance charges.

## Data

Observations: 1,338 individuals

Target variable: Insurance charges (USD)

Predictors: age, BMI, number of children, sex, smoking status, and region (one-hot encoded).

## Methods

1. **Exploratory Analysis**: Charges exhibited strong right skew and extreme outliers.
   
3. **Statistical Models**:

   * Ordinary Least Squares (OLS) on raw and log-transformed charges
   * Robust Linear Model (Huber loss)
     
4. **Predictive Models**:

   * Baseline Linear Regression
   * Ridge and Lasso regression
   * Random Forest Regressor
     
5. **Evaluation**:

   * Train–test split (80/20)
   * Metrics: R² and RMSE
   * 5-fold cross-validation for Random Forest

## Results

**Test Set Performance**:

* Linear Regression: R² = 0.784, RMSE = 5,796
* Ridge Regression: R² = 0.783, RMSE = 5,796
* Lasso Regression: R² = 0.783, RMSE = 5,796
* Random Forest: R² = 0.864, RMSE = 4,587

**Cross-Validation (Random Forest)**:

* Mean R² = 0.837 (SD = 0.032)
* Mean RMSE = 4,853 (SD = 338)

## Feature Importance (Random Forest)

1. Smoking status (≈61%)
2. BMI (≈21%)
3. Age (≈13%)
   Remaining variables each contributed <2%.

## Diagnostics

Residual–prediction plots showed reduced heteroskedasticity relative to linear models, with mild remaining error spread at high charge levels.

## Interpretation

Smoking status dominates insurance cost prediction, followed by BMI and age. This reflects actuarial risk pricing but raises fairness concerns, particularly for behavioral and health-related variables.

## Limitations

* Random Forest lacks interpretability compared to linear models.
* Regional effects may be underestimated due to coarse geographic encoding.
* External validity is limited to populations similar to the dataset.

## Conclusion

The Random Forest model provides the best predictive performance and robustness to outliers. For inference and policy discussion, robust and log-linear regressions remain essential complements.
