# Causal Inference Interpretation for Employee Resignation

In the previous project after clustering employee performance and predicting whether employees will resign or not. Now I'm trying out some projects that have the potential to gain extensive insight into how to deal with employee performance that indicates that they will resign.


## Result:

### Shap Summary Plot on Top 5 Feature
![image](https://github.com/roniantoniius/Causal-Inference-Interpretation-for-Employee-Resignation/assets/121453378/b00789f9-1755-43cc-b79f-bfe06a1ea523)

- the higher the SHAP value owned by a feature, the more correlated the variable is.

Based on the results of the visualization of the SHAP value above which is rotated based on the importances of each variable. There are several variables that have a good value or correlation, such as the top 5 most important features, namely the level of employee satisfaction, the time employees spend with the company, the average total hours worked per month, the number of projects handled, the time of the last job evaluation has a very high probability or very influential on employees to resign, and the amount of salary. But of course this does not mean that these are the driving factors that directly cause employees to resign, there may be hidden variables such as **confounders** that influence the top features and results. For example, there may be some types of departments that have a less conducive environment that cannot achieve goals or an employee is uncomfortable in that environment, causing the employee to resign.

To overcome the possible confounding variables, we can make appropriate improvements, we can train different models to control all possible confounders and study the causal effect for a given feature. The solution to these problems is already available in the Causal Interpretation tool, which will first explain the causal correlation or causal relationship of the top 5 features.

### Causal Inference Evaluation
![image](https://github.com/roniantoniius/Causal-Inference-Interpretation-for-Employee-Resignation/assets/121453378/bc400a83-b4ed-407b-81ef-bcd86642a8d6)

From the summary table and evaluation plot above, it can be seen that the direction of the causal effect is quite linear and in line with the direction of the correlation. But features such as **number_of_projects** and **time_spent_for_the_company** might be the strongest predictors of how likely employees are to **resign**, but I'm not sure that these two features are the ones that definitely signal employees to **resign**.

Such information is hopefully useful for managers when trying to come up with a plan to reduce employee resignation rates, increase employee satisfaction levels, prepare more thoroughly when conducting job evaluations, work on or allocate structured projects, and also optimizing the time spent by employees towards the company may be more effective than just increasing their salary/shares.

### Solution
![image](https://github.com/roniantoniius/Causal-Inference-Interpretation-for-Employee-Resignation/assets/121453378/54a23faa-5dd3-4c8c-be78-34cfe9d93108)

The heterogeneity_tree diagram gives us insight into how the causal influence of the variable **"number_of_projects "** using CATE on outcomes varies among subgroups in the data. Based on the resulting diagram, we can conclude that:

Positive Influence: Employees with a shorter time in the company, a high last evaluation, and low monthly working hours show a positive influence of **"number_of_projects "**. This means that adding new projects tends to improve their performance or satisfaction.

Negative Influence: Employees with moderately low last evaluations or high monthly work hours show a negative influence of **"number_of_projects "**. For them, adding new projects may not be effective and could even decrease performance or satisfaction.

The recommended strategy is to focus on adding and optimizing projects on employees with short time in the company, high expected job evaluations so that they perform well and are expected to be satisfied, and low monthly working hours, while reducing or maintaining the number of projects on employees with low evaluations or high working hours.
