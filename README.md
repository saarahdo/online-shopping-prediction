# 🛒 Online Shoppers Purchasing Intention Analysis
**Task:** Understand what factors influence online purchasing behavior and build a predictive model to estimate the likelihood of a session ending in a purchase.

**Dataset Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset)  
**# of Data points:** 12,330 sessions  
**Target Variable:** `Revenue`

**Author:** Sarah Do  
**Date:** July 28, 2025


#### Objectives:
1. What user behaviors and attributes are associated with completing an online purchase?
2. How can these behavioral insights help improve customer engagement and conversion strategies?
3. How can predictive modeling help the business target high-converting user sessions in real time?

#### Deliverables:

- A clear summary of the business problem and goals
- A description of the dataset, including features and target variable (Revenue)
- Documentation of all data cleaning and preprocessing steps
- Exploratory data analysis (EDA) with visualizations and key behavior trends
- A predictive model to estimate the likelihood of a purchase, with performance metrics
- High-level business recommendations for improving conversion rates based on the findings

#### Skills & Tools Used:

- Data Cleaning & Preprocessing (Pandas, One-Hot Encoding, VIF analysis)
- Exploratory Data Analysis (Seaborn, Matplotlib, Statistical Testing)
- Feature Engineering (Time-based features, engagement ratios, interaction terms)
- Feature Selection (Correlation analysis, multicollinearity recognition, VIF analysis, domain filtering)
- Predictive Modeling (Logistic Regression, XGBoost with hyperparameter tuning)
- Imbalanced Learning and Resampling (SMOTE with multiple sampling strategies)
- Advanced Model Evaluation (Confusion Matrix, F₂ Score optimization, ROC-AUC, Precision-Recall curves, Cross-validation with StratifiedKFold)
- Model Optimization (Threshold optimization, RandomizedSearchCV, feature importance analysis)
- Business Analytics (ROI calculations, implementation roadmaps, risk assessment)
- Reporting & Communication (Clear visual summaries and actionable business insights)

## 🔎 I. Introduction <a name="introduction"></a>
#### General Information:
- This dataset reflects user behavior from an unnamed e-commerce website over a one-year period, likely in 2017–2018, as collected via Google Analytics and published in 2018.
- The target variable (`Revenue`) indicates whether that session resulted in a purchase.

#### Limitations:
- Data collected from 2017-2018. E-commerce user data may have changed since then, so the data may not be timely.
- Because the website identity is anonymized, we won't be able to tie findings to a specific product category or industry.
- Data was collected per unique session, and not per unique user. We are unable to analyze long-term user behavior os customer lifetime value.
- Lack of demographics on customers. There is no way to segment by customer type.
- Severe class imbalance. Only ~15% of sessions resulted in a purchase. Models may overpredict the "no revenue class"
- No product details or marketing data. There is no way to test the effectiveness of a promotion or the impact of marketing on the product. 
- Time-based columns are categorical instead of timestamped. Time series analysis is limited by this. 
- Collected from a single website. These behavioral patterns may not reflect patterns of other websites or industries.

#### Variable Information:
- `Administrative`, `Informational`, and `ProductRelated` represent the number of different types of this unique page was visited.
- `Administrative_Duration`, `Informational_Duration`, and `ProductRelated_Duration` represent the total time spent in each of these pages.
- `BounceRates` represents the percentage of visitors who enter the site from that page and then leave without triggering any other requests.
- `ExitRates` represents the percentage of sessions that ended on that page out of all the sessions that viewed that page.
- `PageValues` represents the average monetary contribution of that specific page toward a completed purchase.
- `SpecialDay` represents a numeric score between 0 and 1 that reflects how close a session's date is to a major. holiday or potentially sales-boosting day. The data author has chosen 6 days before the holiday to be the max score.
- `Month` represents the month the user visited the site. There are 2 missing months: January & April.
- `OperatingSystems` represents the operating system (OS) used by the visitor during their session, where the encoding is most likely categorized as:
    - 1 : Windows
    - 2 : Macintosh (MacOS)
    - 3 : Linux
    - 4 : Chrome OS or other
    - 5+ : Other
- `Browser` represents an integer encoding on the web browser used by the visitor during their session where the encoding is most likely categorized as:
    - 1 : Chrome
    - 2 : Firefox
    - 3 : Internet Explorer
    - 4 : Safari
    - 5+ : Other / Mobile Browser
- `Region` represents the geographical region or location of the user. Because the data is anonymized, the specific regions are unknown.
- `TrafficType` represents the type of referral traffic that brought the user to the website, encoded as an integer, where the encoding is most likely categorized as:
    - 1 : Direct (typed URL)
    - 2 : Organic Search
    - 3 : Paid Ads
    - 4 : Referral
    - 5+ : Other
- `VisitorType` represents whether the customer is a returning or new visitor.
- `Weekend` represents a boolean value where 1 = is weekend and 0 = is not weekend.
- `Revenue` represents a boolean value where 1 = completed purchase and 0 = abandonded.

