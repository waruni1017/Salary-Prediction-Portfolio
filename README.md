Exploring salary for different Job postings and Predicting salary.

Introduction

Let it be Students in high school, parents who have young children, recent graduates seeking jobs. Many in the modern world, wonder and keen to know what educational qualification, what industry and/or what job may provide the desired salary they are looking for. Even the employers may also benefit knowing salary for different job postings. That way it would open space for them to negotiate properly when the time comes.

In this project I develop 3 models, namely multiple linear regression, random forest regression and gradient boosting regression, and identify the best out of these, comparing the mean square errors.

Dataset

There are 10,000,000 data. And the dataset contains several variables.
jobId		 	: job identification number 
companyId	 	: company identification number
jobType	 	: types of positions (categorical)
degree		 	: highest level of education qualification (categorical)
major		 	: field majored in education (categorical)
industry		: Industry of the job (categorical)
yearsExperience          : years of experience in the candidate (numerical)
milesFromMetropolis : distance from metropolis in miles (numerical)
salary			: salary in thousands for each candidate (numerical)

Data Preprocessing

First, I prepared data by checking for duplicates and invalid data. There were no duplicates, however there were 5 entries with 0 salaries. When inspected further these data points were associated with such job types and industries where 0 salary doesn’t make any sense, so I removed them. Now the dataset has 999995 data in the set.

Exploratory Data Analysis

Before building machine learning algorithms, I performed exploratory data analysis to identify any significant features affecting the salary. 
Just like one would expect, data shows that higher the rank in a company, higher the salary is. Also, people with higher education level tend to earn more, which is also pretty obvious. What was interesting to learn that is people who majored in engineering, business seem to be earning decently when compared with other fields. 

Also, data set uncovers that, in the modern world, people in oil industry is being paid more. One would think, as an effect of the digital revolution on society, web industry going far ahead with other industries. However, according to this data set it has earned the 3rd place while oil industry and finance industry acquiring 1st and 2nd respectively.
 
I also examined how years of experience and distance from metropolis affect the salary. And the results make sense. Years of experience is directly proportional to the salary whereas the distance form metropolis is inversely proportional to the salary.

It is pretty noticeable that the salary distribution looks symmetric. However, when screening the boxplot, it can be observed that there are some outliers in the upper end. When explored further, I noticed that these data might be useful for the machine learning models I was planning to develop. So, I decided not to drop them.

Modeling

Since most of my feature variables are categorical, I decided to one-hot code all categorical variables. And then I chose a 2/3-1/3 train and test for modeling.
Following are the models and respective mean square errors:

Multiple Linear Regression	384.2013
Random Forest 	366.7268
Gradient Boosting	359.4175

Conclusion

Comparing the mean square error each model produced, gradient boosting seems to be a good fit for data. 

•	When the feature importance is checked, I discovered that jobType_janitor being the most important out of all features. This is interesting, at the same time, this could make someone think why??

•	One more compelling point to observe would be to see how the outliers we saw in the salary distribution could alter these results?
