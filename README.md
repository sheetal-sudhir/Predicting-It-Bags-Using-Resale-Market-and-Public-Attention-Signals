# Predicting “It Bags” Using Resale Market and Public Attention Signals

## Overview
This project predicts which luxury handbags will become culturally iconic “It Bags” using resale market data and public attention signals.

We frame the problem as a **binary classification task** and evaluate whether early signals from resale platforms and Google Trends can predict future resale dominance.

---

## Dataset
- Source: Rebag resale listings + Google Trends
- Raw data: ~114,000 listings
- Final dataset: **328 handbag models**
- Features: **28 model-level features**
  - Pricing (resale price, retail price)
  - Engagement (views, favorites)
  - Condition & style
  - Public attention (Google Trends)

- Label:
  - `it_bag = 1` if resale premium is in top 20%

---

## Models
We evaluate:

- Logistic Regression (L1, L2)
- Random Forest
- Gradient Boosting

Evaluation metric:
- **AUPRC (Area Under Precision-Recall Curve)**

---

## Results

| Model | Validation AUPRC | Holdout AUPRC |
|------|------|------|
| Logistic Regression (L1) | 0.752 | 0.879 |
| Gradient Boosting | 0.748 | **0.920** |
| Random Forest | 0.746 | 0.845 |
| Logistic Regression (L2) | 0.731 | 0.915 |

Key findings:
- Strong performance despite class imbalance
- Simple models perform comparably to complex ones
- Pricing + attention signals are highly predictive

---

## Interpretability
- SHAP analysis shows:
  - Resale price
  - Engagement metrics
  - Google Trends
  are the most important features

---

## Key Insights
- Market signals alone are highly predictive
- Public attention provides additional signal
- SMOTE does not improve performance → dataset already informative

---

## How to Run

```bash
pip install -r requirements.txt
