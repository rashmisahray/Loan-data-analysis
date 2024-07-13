Data Preprocessing and Analysis Report
Data Preprocessing
Loading and Initial Inspection
The first step in our data preprocessing involved loading the original CSV file (loan_dataset.csv) into a Pandas DataFrame.
This was followed by creating a copy of this DataFrame, named df_filled, which was used for filling null values.
The initial inspection included checking the structure, summary statistics, and identifying columns with null values.
Identifying and Filling Null Values
After identifying the columns with null values and their respective counts, various strategies were employed to handle them:

Dependents: Null values were replaced with 0. This decision was based on the assumption that missing values in this context likely indicate no dependents.
Loan Sanction Amount (USD): Null values were interpolated linearly to maintain the sequence and trends in the data.
Credit Score: Null values were filled with the mean value. This method was chosen after plotting histograms and boxplots to check for skewness, ensuring the mean was an appropriate measure.
Property Location: Null values were filled with 'Undisclosed' to indicate missing data without making assumptions.
Current Loan Expenses (USD) and Income (USD): Null values were filled with the median value. The median was chosen after assessing skewness to avoid the influence of outliers.
Type of Employment: Null values were filled based on Profession using a mapping dictionary to ensure logical consistency.
Has Active Credit Card and Income Stability: Null values were filled with 'Not Active' and 'Unrecorded' respectively to indicate missing information without making assumptions.
Property Age: Null values were filled with the mean of Income (USD), assuming a relationship between income and property age.
Gender: Rows with null values in the Gender column were dropped to maintain the integrity of gender-related analyses.
Saving the Processed Data
The DataFrame with filled null values is saved to a new CSV file Loan_null_removed.csv.

Outlier Detection and Handling
Loading and Identifying Numerical Columns
The new CSV file Loan_null_removed.csv is loaded.
Numerical columns are identified for outlier handling.
Handling Outliers
Outliers are handled using the IQR (Interquartile Range) method:

Outliers in each numerical column are replaced with the mean value if they fall outside the bounds.
Outliers are detected, displayed, and removed for specific columns.
Saving the Final Cleaned Data
The final cleaned DataFrame with handled outliers is saved to Loan_final_cleaned.csv.

Exploratory Data Analysis (EDA)
Univariate Analysis
Histograms
Histograms are ideal for visualizing the distribution of numerical columns as they provide a clear view of the frequency of data points within specified ranges. This helps identify patterns, skewness, and outliers. Histograms for various numerical columns are plotted to visualize the distribution:

Age: To understand the distribution of borrowers' ages.
Income (USD): To observe the spread and central tendency of income values.
Credit Score: To identify the distribution and detect any anomalies in credit scores.
Current Loan Expenses (USD): To analyze the spread of current loan expenses among borrowers.
Loan Amount Request (USD): To see the distribution of requested loan amounts.
Loan Sanction Amount (USD): To visualize how loan sanction amounts are distributed.
Property Price: To understand the range and frequency of property prices.
Density Plot
Density plot provides a smoothed representation of the data distribution, making it easier to observe the overall shape and identify any potential skewness.

Property Age: To visualize the distribution of property ages in a smoothed manner.
Pie Charts
Pie charts are effective for showing the proportionate distribution of categorical columns, making it easy to compare the relative sizes of different categories.

Gender: To illustrate the gender distribution of borrowers.
Income Stability: To show the proportion of borrowers with stable vs. unstable income.
Has Active Credit Card: To display the proportion of borrowers with active credit cards.
Property Type: To depict the distribution of different property types among borrowers.
Bivariate Analysis
Scatter Plots
Scatter plots are used to explore relationships between pairs of variables. They help identify correlations, trends, and potential outliers.

Income vs Loan Amount Request: To examine the relationship between income and requested loan amount.
Income vs Loan Sanction Amount: To explore how income correlates with the sanctioned loan amount.
Credit Score vs Loan Amount Request: To see if there is a trend between credit score and requested loan amount.
Credit Score vs Loan Sanction Amount: To investigate the relationship between credit score and sanctioned loan amount.
Income vs Credit Score: To identify any correlation between income and credit score.
Bar Plots
Bar plots are useful for visualizing relationships between categorical and numerical variables, as they show the average value of the numerical variable for each category.

Loan Sanction Amount (USD) by Property Location: To compare the average loan sanction amount across different property locations.
Income (USD) by Type of Employment: To observe how income varies by employment type.
Loan Amount Request (USD) by Profession: To see the differences in loan amount requests across various professions.
Multivariate Analysis
Complex Scatter Plots
These plots visualize relationships involving three variables, providing a comprehensive view of interactions within the data.

Income vs Loan Amount Request vs Loan Sanction Amount: To examine how income and loan request relate to the sanctioned loan amount.
Credit Score vs Loan Amount Request vs Loan Sanction Amount: To explore the interaction between credit score, loan request, and sanctioned loan amount.
Income vs Current Loan Expenses vs Loan Amount Request: To see how income and current loan expenses influence the loan amount request.
Grouped Bar Plot
Grouped bar plots show the relationship between multiple categorical variables and a numerical variable, highlighting differences across groups.

Income Stability vs Profession vs Loan Sanction Amount (USD): To compare the average loan sanction amount across different professions and income stability statuses.
Grouped Box Plots
Box plots are used to display the distribution of a numerical variable across different categories, showing the spread, central tendency, and potential outliers.

Income (USD) by Type of Employment and Gender: To analyze the income distribution across different employment types and genders.
Current Loan Expenses (USD) by Income Stability and Property Type: To see the variation in current loan expenses across different income stability statuses and property types.
