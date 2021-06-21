<u>Title of the project</u> <b> Carnegie's classification of higher education and Undergraduate programs in US.</b>

<u><i>Read me first</u></i>

This is my independent final class project for the course: Multivariate Statistical Analysis - Stat 730 Fall 2020. The computations and statistical analysis were performed using R studio and R markdown. 

Please click the drop down menus below to further explore this project.

<details><summary>What is Carnegie Classification of Higher Education?</summary>

According to the US News and World Report, there are 4,298 degree-granting post-secondary institutions in the US. Among them, 418 are doctoral universities as classified by the Carnegie Classification of Institutions of Higher Education and to narrow it down, only 131, 135, and 152 of those 418 schools have respectively R1, R2, and R3 (D/PU) distinction. By the definition of Carnegie Classification, the R1 is a category of doctoral universities that have very high research activities, the R2 is a category of doctoral universities that conduct high research activities but at the magnitude, less than that of the R1 type, and finally the R3 is a class of doctoral universities which award professional degrees or Ph.D. degrees with low research activities.

</details>

<details><summary>Getting Data</summary>
Data for the school year 2018-2019 from 357 doctoral universities were used in this study. The data was obtained from College Scorecard, an online tool created by the United States government for consumers to compare the cost and value of higher education institutions in the United States (US).
The data selected is a subset of the <a href="https://data.ed.gov/dataset/college-scorecard-all-data-files-through-6-2020/resources?resource=823ac095-bdfc-41b0-b508-4e8fc3110082"> original data</a>. Our subset only contains information for those US universities that are classified as R1, R2 or R3 by the Carnegie Classification of Higher Education.
</details>

<details><summary>Variables Used</summary>
The variables of the data with their abbreviations are as follows:
<ol><li>INST_NAME – Name of the Institution</li>
<li>STATE – State Abbreviation</li>
<li>CONTROL – Type of Institution: 1 = Public and 0 = Private</li>
<li>STATE_FIPS – FIPS Code of the state where the school is located</li>
<li>CC_BASIC – 2018-2019 Carnegie Basic Classification: R1 = Doctoral Universities with very high research activities, R2 = Doctoral Universities with high research activities, and R3 = Doctoral/Professional universities</li>
<li>FAM_INC – Median Family Income of undergraduate students</li>
<li>SAT_AVG – Average SAT scores</li>
<li>ADM_RATE – Admission Rate</li>
<li>UG_ENRL - Enrollment of undergraduate certificate/degree-seeking students</li>
<li>AVG_FAC_SAL – Average faculty salary per month calculated in 2015 real dollars</li>
<li>RET_RATE – Full-time retention rate</li>
<li>AVG_GRANT – Percentage of full-time, first-time degree/certificate-seeking undergraduate students awarded a Pell Grant</li>
<li>MD_EARN_10 – Median Earnings of the graduates after 10 years of working</li>
<li>MN_EARN_10 – Mean Earnings of the graduates after 10 years of working</li>
<li>UNEMP_RATE – An unemployment rate of graduates after a year of graduating</li>
<li>GRAD_DEBT_MDN – Median graduate debts at the time of graduation</li>
<li>GRAD_RATE_6 – Degree Completion rate for first-time, full-time students at four-year institutions (150% of the expected time to completion)</li> 
<li>GRAD_RATE_4 – Degree Completion rate for first-time, full-time students at four-year institutions (100% of the expected time to completion)</li>
</ol>

</details>

<details><summary>Motivation (Main Question of the study)</summary>
If it were for a graduate, especially a doctoral applicant, to choose among these three research categories of universities, the choice of an R1 school should be obvious because enrolling in an R1 school’s graduate program would mean more extensive research and funding opportunities along with the privilege to work with some highly qualified faculty. However, how would it be the case for an undergraduate applicant? Like doctoral students, do undergraduate students have any significant advantage for choosing an R1 school over an R2, or an R2 school over an R3? Or does the Carnegie classification even matter when it comes to undergraduates’ degree outcomes? The big picture of this research is to inform future college applicants about the degree outcomes based on the classification of the universities in the US which can give them an idea if they should follow the graduate applicants’ most desired category of schools, R1.
</details>

<details><summary>Objectives</summary>
This study has the following objectives:
<ol>
<li>To classify universities based on institutional size and performance. The subjects of the study are approached from the perspectives of admission rate, enrollment size, graduation rate, post-graduation income, and the unemployment rate among the graduates. </li>
<li>To predict and compare graduation rate within 6 years, median debt at the time of graduation, and graduates median income after 10 years among the three categories of research universities.</li>
</details>
<details><summary>Methods</summary>
To address the goals of this study, the following multivariate methods were used:
<blockquote>
<details style="margin-left: 40px"><summary>Principal Component Analysis (PCA)</summary>
The data set chosen for this project contains 18 variables (Appendix I). Not only it can be tedious to analyze all the variables for the analysis, but some information may be of little importance in addressing our study goals. Hence, through PCA, the variance-covariance structure of a set of variables through a few linear combinations of these variables was explained. As the variables in our dataset had different measurement units, the PCA was conducted using normalized variables. Two principal components were used in the continuous variables of this study. The first PCA was performed in the overall data to aid the subsequent analysis, discrimination, and classification. The second PCA was employed in the original data set without the predictor variables. Besides, a scree plot of each PCAs was obtained which suggested how many Principal Components (PCs) to choose from. The PCs that equaled maximum variation in the original data set without predictor variables were then merged with a dataset that contained only the original three predictor variables, to use the newly formed data set for multivariate regression analysis.
</details>
<details style="margin-left: 40px"><summary>Discriminant and Classification Analysis</summary>
Using an R-package ‘MASS’, a linear discrimination analysis was applied to find some variables within our dataset that best distinguishes between the three categories of universities. A linear discriminant was chosen over a quadratic as the former gave less estimated actual error rate (AER) and since our values are from the PCA, common covariance among the variables is assumed.
</details>
<details style="margin-left: 40px"><summary>Multivariate Regression</summary>
Using the PCs resulted from a PCA on the original dataset as predictors, a multivariate regression model was used to predict graduation rate, graduate’s debt, and graduates' median earning after 10 years of working, among the three types of research institutions. The uncertainty of this prediction was quantified using a 95% confidence interval.
</details>
<blockquote/>
</details>

<details><summary>Conclusion</summary>
The linear discriminant analysis (LDA) showed some promising results on distinguishing among the type of the research universities and the undergraduates’ outcomes, the prediction based on the MANOVA test gave us contrasting results that is a student with a higher SAT score had a greater chance of graduating within 6 years in a lower-tier school while incurring similar amount of debt and accumulating similar decade long earning prospect to that of higher tier universities. Hence, based on the results above we found no significant evidence that the undergraduate students have better graduation rates and post-graduation outcomes at a higher tier school.
</details>
