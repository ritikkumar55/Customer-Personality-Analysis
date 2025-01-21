# Customer Personality Analysis for Market Segmentation

## Overview
This project focuses on performing a detailed analysis of customer data to identify distinct segments using clustering techniques. By understanding customer behaviors and preferences, businesses can enhance their marketing strategies and provide personalized experiences, resulting in better customer satisfaction and optimized resource allocation.

---

## Problem Statement
Customer Personality Analysis helps businesses:
- Understand customer preferences and behaviors.
- Identify target customer segments for specific marketing campaigns.
- Optimize product offerings and promotional strategies based on customer needs.

Instead of marketing new products to every customer, businesses can identify specific segments likely to respond positively, reducing costs and improving conversion rates.

---

## Dataset
The dataset contains customer details across various features:

### Key Features:
1. **Demographics:**
   - `ID`: Unique customer identifier.
   - `Year_Birth`: Customer's year of birth.
   - `Education`: Education level (e.g., Graduation, PhD).
   - `Marital_Status`: Marital status (e.g., Single, Married).
   - `Income`: Annual household income.

2. **Household Information:**
   - `Kidhome`: Number of children.
   - `Teenhome`: Number of teenagers.

3. **Engagement Data:**
   - `Recency`: Days since last purchase.
   - `Dt_Customer`: Customer's enrollment date.

4. **Purchase Behavior:**
   - `MntWines`, `MntFruits`, `MntMeatProducts`, etc.: Amount spent on different product categories in the last 2 years.
   - `NumWebPurchases`, `NumCatalogPurchases`, `NumStorePurchases`: Purchase count across channels.

5. **Campaign Response:**
   - `AcceptedCmp1`, `AcceptedCmp2`, etc.: Campaign acceptance indicators.
   - `Response`: Acceptance of the last campaign.

---

## Approach

### 1. **Data Preprocessing:**
- **Handling Missing Values:** Replaced missing `Income` values with the median due to its skewed distribution.
- **Feature Engineering:**
  - Combined child and teenager counts into a single `Kids` feature.
  - Created `Expenses` by summing spending across all product categories.
  - Extracted customer registration duration (`Customer_For`).
  - Calculated `Customer_Age` using the current year and `Year_Birth`.
- **Encoding Categorical Features:** Converted `Education` and `Marital_Status` into numerical labels.
- **Scaling:** Used StandardScaler for scaling numerical features.

### 2. **Exploratory Data Analysis (EDA):**
- Analyzed relationships between:
  - Income and Expenses
  - Number of Kids and Expenses
  - Marital Status and Expenses
- Visualized data using bar plots, scatter plots, and heatmaps.

### 3. **Clustering Techniques:**
- **K-Means Clustering:**
  - Used the Elbow Method to determine the optimal number of clusters (k=2).
  - Cluster Characteristics:
    - **Cluster 1:** Cost-conscious customers with low income and more kids.
    - **Cluster 2:** High-spending customers with higher income and fewer kids.

- **Agglomerative Clustering:**
  - Reduced dimensions using PCA for better clustering accuracy.
  - Validated clusters using visualizations and comparisons with K-Means results.

---

## Results
1. **Key Insights:**
   - High-income customers with fewer children (Cluster 2) spend more and are ideal for targeted marketing.
   - Cost-conscious customers (Cluster 1) can be engaged through budget-friendly campaigns.

2. **Visualization:**
   - Cluster distribution was visualized using scatter plots and 3D PCA projections.

---

## Tools & Libraries
- **Languages:** Python
- **Libraries:**
  - Data Analysis: `pandas`, `numpy`
  - Visualization: `matplotlib`, `seaborn`
  - Machine Learning: `scikit-learn`

---

## How to Run
1. Clone the repository:
   ```bash
   git clone <repository_url>
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the Jupyter Notebook or Python script for analysis:
   ```bash
   jupyter notebook analysis.ipynb
   ```

---

## Conclusion
This project demonstrates how clustering techniques can effectively segment customers based on their personality, spending habits, and preferences. These insights help businesses optimize their marketing strategies, reduce costs, and improve customer satisfaction.

---

## Future Scope
- Incorporate advanced clustering methods like DBSCAN for non-linear clusters.
- Use predictive modeling to recommend personalized products to customers.
- Analyze temporal trends in customer behavior for dynamic segmentation.

---

