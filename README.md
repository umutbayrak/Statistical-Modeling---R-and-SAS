# Statistical-Modeling---R-and-SAS
A regression analysis using R and SAS for an assignment

This homework consists of a data analysis performed in SAS, and a 'theoretical' exercise that can be approached through simulation (in R), plus two small questions.

1. A SAS Exercise
The dataset caschoolvar3.xlsx contains a random sample of California elementary school districts. The data consists of test scores ( Y: testscr ), class sizes (X1: stratio ) and variable X2 ( nonep ) recording the percentage of non-native English speakers among the students in each district.

The test score is a districtwide average of reading and math scores on the Stanford achievement test, a test utilized by school districts in the USA. The student-teacher ratio, i.e. the total number of students in the district divided by the number of teachers, is used as a measure of the (overall ) class size in the district. Policy makers wish to know whether reducing class size, for instance by hiring more teachers, improves the student's education. Skeptics worry that reducing class size will increase costs without producing substantial benefits. The aim of this homework is to study the association between the two variables, first by fitting a simple linear regression model Yi = B0 + B1 . Xi + Ei satisfying all the usual assumptions, then by adjusting for the percentage of non-native English
speakers among the students in each district.

1. Explore the variables in the model to get a better understanding of their distribution and of the bivariate relationships. Describe briefly your findings

2. First, for the simple linear regression of test scores on class sizes, answer the
following questions:

(a) Give the parameter estimates, their standard deviations and their 95% confidence intervals.
(b) Give a clear and useful interpretation of the estimated regression coefficients.
(c) Calculate a 95% confidence interval of the regression slope and interpret the interval.
(d) Perform a two-sided statistical hypothesis test to test the hypothesis that the regression slope is zero (use alpha = 0.05). Interpret the result.
(e) Assess the assumptions underlying the linear regression model (scope of the model, study of outliers and residuals, linearity of the curve, constancy of the variance, lack-of-fit, ...), and discuss the model quality.
3. Next, fit a multiple linear regression model with stratio and nonep as explanatory variables (no interaction).

(a) Discuss briefly your results (e.g. interpretation of parameters, quality of the model fit, outliers, assess model assumptions...).

(b) Relate the findings with your results from the simple linear regression with only stratio as explanatory variable. Compare the estimates of the key regression coefficient and quality of the model fit between the two models. What is the difference in interpretation of the regression coefficient of stratio ? Explain the issue of confounding in this particular context.
(c) Fit again a multiple linear regression model with stratio and nonep, but now also include their interaction effect. What is the interpretation of the parameter estimates? Please present the results of your analysis also graphically in a way that the reveals the key features to a non- statistician.
(d) Suppose a schooldistrict has a student-teacher ratio of 20 and 50% of non native English speakers. What is the predicted score for such a schooldistrict. Report the outcome with a 95% prediction interval.
(e) Write an executive summary containing the main conclusions from your analysis, including main discussion points, as they pertain to the original research question (max. 1=2 page).

2. R - A Simulation Exercise to explore the impact of confounding and interaction

In a clinical study, physicians are interested in the effect of a new treatment on the blood pressure. In a random sample from the population of patients for whom the treatment was prescribed, they observe patients who use the new treatment and patients who do not. On the other hand, a certain gene is known to have an extreme influence on the blood pressure. In this exercise, we aim to find out what happens when the treatment effect is estimated with and without accounting for the gene effect.

Suppose that the blood pressure is modelled correctly by the following population
model: Yi = B0 + B1x1i + B2x2i + B3x1ix2i + Ei (1) where Ei ~ N(0; sigma^2) (i = 1; : : : ; n) ar independent random variables. Yi is
the blood pressure for individual i, x1i indicates whether person i uses the new treatment (x1i=1) or not (x1i=0) and x2i = 1 (x2i = 0) indicates the presence (absence) of the gene. Assume that there are no further confounders of the effect of x1i on Yi after adjusting for x2i: In the random sample from the population we have:

P(X2i = 1 | X1i = 0) = q0
P(X2i = 1 | X1i = 1) = q1;

with 70% of the patients taking the treatment.

You are asked to explore answers to the following questions by simulation or theoretically.

(a) Model (1) represents the true data-generating model, but this is of course
unknown to the statistician. Suppose we analyze the data instead with
the model
Yi = ~ B0 + ~ B1x1i + ~ B2x2i + Ei (2)
where Ei ~ N(0; sigma^2) (i = 1.....n).

i. Using the true data-generating model (1), chose and fix any parameter values you need, and find the (approximate) average causal effect of the treatment on the blood pressure for xed levels of x2, separately for patients with the genotype and for patients without the genotype.
ii. Does estimating the effect of x1 on Y given x2 based on model (2) result in unbiased estimates of these causal eects ? Explain.
iii. How does the variance (and hence precision) compare. Can you say something about the mean squared errors?

Are the following statements right or wrong? Please explain your answer.
(a) Based on a regression analysis with one regressor and slope B1 , the null hypothesis H0 : b1 = 0 is rejected in favour of the alternative H1 : B1 > 0 with a very small p-value (p < 0:0001). The fitted model will thus give very good predictions.
(b) In a study the subject's age is known to be a confounder. The statistician includes age as a covariate in the regression model, but it turns out that the regression coefficient of age is not significant at the 5% level of significance (say, p = 0.69). He/she can therefore remove age from the model.
