# 📊 Smart Loan Recovery Strategy (Using Machine Learning)

This project uses **Machine Learning and Data Analysis** to help financial institutions identify high-risk borrowers and recommend suitable recovery strategies.  

---

## 📌 Project Overview
Banks often face challenges in recovering loans from borrowers who default on their payments.  
Using Python, visualization tools & ML algorithms, I tried to:
- Analyze borrower profiles and loan repayment behavior  
- Segment borrowers into distinct **risk categories**  
- Predict whether a borrower is **high risk** or **low risk**  
- Suggest **personalized recovery strategies** based on predicted risk
  
---

## 📂 Dataset
The dataset contains **500 borrower records** with features such as:
- Age, Gender, Employment Type  
- Monthly Income, Loan Amount, Loan Tenure, Interest Rate  
- Collateral Value, Outstanding Loan Amount, EMI  
- Payment History, Missed Payments, Days Past Due  
- Recovery Status, Collection Attempts, Legal Action  

---

## 📊 Exploratory Data Analysis (EDA)
Some of the key insights:
- **Higher incomes generally correlate with higher loan amounts**, but some high loans are still given to low-income borrowers.  
- **Payment history** strongly affects recovery status – on-time payers recover, while missed payments often end in defaults.  
- **Boxplot analysis** of missed payments shows partially recovered loans usually have fewer missed payments than written-off loans.  
- **Scatter plots** between income and loan amounts reveal recovery trends among different borrower groups.  

---

## 🤖 Machine Learning Approach
1. **Feature Scaling**: Standardized numeric features using `StandardScaler`.  
2. **Clustering with KMeans**:  
   - Optimal clusters: **4**  
   - Segments identified:  
     - Low Income, Low Loan, Low Risk  
     - High Loan, Higher Default Risk  
     - Moderate Income, Medium Risk  
     - High Income, Low Default Risk  
3. **Label Encoding**: Borrowers were flagged as:  
   - **1 = High Risk** → ‘High Loan, Higher Default Risk’, ‘Moderate Income, Medium Risk’  
   - **0 = Low Risk** → ‘Low Income, Low Loan, Low Risk’, ‘High Income, Low Default Risk’  
4. **Random Forest Classifier**:  
   - Chosen for its robustness with imbalanced features and ability to provide **feature importance**.  
   - Most important predictors:  
     - Days Past Due  
     - Monthly EMI  
     - Loan Amount  
     - Number of Missed Payments  

---

## 📈 Results
- Model predicts borrower **risk scores** (0 → Low risk, 1 → High risk).  
- **Feature Importance Ranking** shows repayment behavior features (missed payments, days past due) are stronger predictors than demographic info.  
- Borrowers are assigned a **Recovery Strategy** based on predicted risk:  
  - **Low Risk** → Automated reminders & monitoring  
  - **Medium Risk** → Settlement offers & repayment plans  
  - **High Risk** → Immediate legal notices & aggressive recovery  

---

## 🛠 Tech Stack
- **Python**: Pandas, Scikit-learn  
- **Visualization**: Matplotlib, Seaborn  
- **ML Models**: KMeans, Random Forest Classifier  

---
