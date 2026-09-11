# Crop_Yield_Prediction

# Crop Yield Prediction Pipeline

A robust machine learning pipeline designed to predict agricultural crop yield (`Crop_Yield_ton_per_hectare`) using environmental, soil, and climate features. 

---

## 📊 Project Overview
* **Dataset Size:** 10,000 rows, 20 initial features (numeric & categorical).
* **Target Variable:** `Crop_Yield_ton_per_hectare` (originally exhibiting right-skewness with a skewness of 1.59).
* **Final Model:** Linear Regression with Log-Transformed Target (`np.log1p`).
* **Performance:** $R^2 \approx 0.98$, with exceptionally stable cross-validation scores and zero overfitting.

---

## 🛠️ Feature Engineering
To capture non-linear relationships and agronomic dynamics from raw parameters, the following custom features were engineered:
1. **`Total_NPK`**: Total sum of macro-nutrients ($N + P + K$).
2. **`N_K_Ratio`**: Nitrogen-to-Potassium balance ratio.
3. **`Climate_Interaction`**: Combined effect of temperature and humidity.
4. **`Water_Index`**: Interaction between rainfall and soil moisture.
5. **`Evaporation_Proxy`**: Sunlight hours adjusted by wind speed.

---

## 📈 Model Performance & Validation

| Metric | Train Set | Test Set | 5-Fold Cross-Validation |
| :--- | :--- | :--- | :--- |
| **$R^2$ Score** | — | **0.9816** | **0.9806 ($\pm 0.0007$)** |
| **RMSE** | 2.8821 ton/ha | 2.7961 ton/ha | — |
| **MAE** | 1.7151 ton/ha | 1.6626 ton/ha | — |

> **Key Takeaway:** The model demonstrates exceptional generalization capabilities with test errors matching or outperforming training errors, confirming the complete absence of overfitting.

---

## 🚀 Getting Started

### Prerequisites
Make sure you have the required libraries installed:
```bash
pip install numpy pandas scikit-learn matplotlib seaborn scipy
