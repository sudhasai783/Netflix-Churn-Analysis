# Netflix Customer Churn Prediction 🎬📉

## 📌 Project Overview  
Customer churn is one of the biggest challenges for subscription-based businesses like Netflix.  
In this project, I built a machine learning pipeline to **predict customer churn** and **identify key factors driving attrition**.  

The goal was to not only classify churners vs non-churners but also extract insights that can help businesses **improve retention strategies**.  

---

## 📂 Dataset  
- **Source:** Synthetic Netflix-like dataset (~5,000 customers)  
- **Target:** `churned` (0 = active, 1 = churned)  
- **Key Features Used:**  
  - `age`, `gender`  
  - `subscription_type` (Basic, Standard, Premium)  
  - `watch_hours`, `avg_watch_time_per_day`  
  - `last_login_days`  
  - `monthly_fee`  
  - `number_of_profiles`  
  - `region`  

---

## 🛠️ Tools & Libraries  
- **Python** (pandas, numpy)  
- **Scikit-learn** (Logistic Regression, Random Forest, XGBoost)  
- **Matplotlib / Seaborn** (visualizations)  
- **Jupyter Notebook**  

---

## 🔎 Exploratory Data Analysis (EDA)  
- Churn rate distribution (~50%)  
- Engagement features (`watch_hours`, `last_login_days`) showed strong correlation with churn  
- Categorical churn rates (Premium < Standard < Basic)  

---

## ⚙️ Modeling Approach  
1. **Preprocessing**  
   - OneHotEncoding for categorical features (`gender`, `subscription_type`, `region`)  
   - StandardScaler for numerical features  
   - Pipeline setup for clean transformation  

2. **Models Tested**  
   - Logistic Regression → baseline (interpretable)  
   - Random Forest → feature importance + non-linearities  
   - XGBoost → boosting for higher accuracy  

3. **Evaluation Metrics**  
   - Confusion Matrix  
   - Precision, Recall, F1-score  
   - ROC-AUC  

---

## 📊 Results  
- **Logistic Regression:**  
  - Accuracy: **89%**  
  - ROC-AUC: **0.88**  
  - Recall (churn): **0.90** (catches most churners)  

- **Key Drivers of Churn (Feature Importance):**  
  - 📉 Low `avg_watch_time_per_day` → increases churn  
  - 📉 Low `watch_hours` → increases churn  
  - 📈 High `last_login_days` → increases churn  
  - 📉 Fewer `number_of_profiles` → increases churn  
  - 📉 Subscription type → Premium users less likely to churn  

---

## 📈 Visualizations  
- Confusion Matrix  
- ROC Curve  
- Precision-Recall Curve  
- Feature Importance (Logistic Regression coefficients + Random Forest importances)  

---

## 🎯 Business Impact  
- Identified **engagement metrics** (watch time, login frequency) as the strongest predictors of churn.  
- Suggested **retention strategies**:  
  - Target low-engagement users with personalized recommendations.  
  - Encourage multi-profile usage to reduce churn.  
  - Incentivize long-inactive users with reactivation offers.  

---

## 🚀 Next Steps  
- Hyperparameter tuning with GridSearchCV  
- Test more advanced models (LightGBM, Neural Nets)  
- Deploy churn prediction model as a **Flask/FastAPI web app**  


