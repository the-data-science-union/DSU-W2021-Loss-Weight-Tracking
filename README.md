# Weight Loss Tracking

## Project Goals
1. Our primary goal aims to train a linear regression machine learning model which predicts the average daily calorie consumption based on an individual’s average daily activity information, such as daily walking steps, walking distance, very active minutes and so on.
2. Our secondary goal aims to train an ensemble regression learning model given the same dataset to explore how we can combine multiple regression models to improve the accuracy and overall performance of prediction beyong linear regression.
3. Lastly, we hope to create an interactive and engaging atmosphere for our members to share ideas, tell stories, practice ML skills, strengthen leadership, teamwork and communication skills.


## Logo
<img src="./logo.jpg" width= "300" height = "300" >

## Exploratory Data Analysis



## Analysis of Linear Regression
We built several models to test out which method was the best at capturing the relationship between specific activities and the number of calories burned. During the process, we found that our linear model with 7 predictors had the highest test R^2 of 0.74. Since the scale for each predictor is standardized, we can directly compare the coefficients. The two largest contributors are TotalDistance and TotalSteps which makes sense as they were highly correlated with the target Calories. In the graph, the line for the predicitons is fairly close to the 45 degree line which is what we hoped for.

![Real vs Predicted](Visualizations/real_vs_predicted.PNG)

Going further into the details, we can look at the diagnostic plot to quanitfy the 7-predictor model's performance. In the Residuals vs Fitted graph, we can see that the red line curves near the end however this isn't a serious violation. Next in the Normal Q-Q figure, we expect to see a straight light and for the most part it is until the deviations near the tail. The 3rd plot, Scale-Location, is also supposed to be flat with equally spaced points, but data isn't perfect. Lastly, there's 2 points in the Residuals vs Leverage figure that could be bad leverage. However, when we tried building a model on data with the outliers removed, the R^2 value didn't improve much so we just left it.

<img src="./Visualizations/residual_vs_fitted.PNG"><img src="./Visualizations/normal_qq.PNG">
<img src="./Visualizations/scale-location.PNG"><img src="./Visualizations/residuals_vs_leverage.PNG">

Besides those, we also calculated the Variance Inflation Factor (VIF) scores to measure how correlated the predictors were. All of them except VeryActiveMinutes and SedentaryMinutes are very high and this is reflected on the correlation map as well. So this meant that despite our model's relatively high scores, it wasn't our most reliable model.

![VIF Scores](Visualizations/VIF.PNG)

The reason why we went with a 7 predictor model was because it had the highest R^2 score. Will, one of the data analysts, conducted two tests: AIC and BIC. This is a test where we're trying to find the lowest AIC and BIC scores to determine the ideal number of predictors to include in the model. Both graphs gave similar results, showing the lowest AIC/BIC scores after 7 predictors. Expanding upon this, we decided on 7 instead of 8+ so as to avoid overfitting the model. 

<img src="./Visualizations/AIC.png" width= "400" height = "300"><img src="./Visualizations/BIC.png" width= "400" height = "300">

## Analysis of Emsemble Regression 




## Summary 

1. We built two linear regression models to predict the average daily calorie consumption. In terms of statistical significance and validity, the second model runs into less issues of multicollinearity measured by variance inflation factor (VIF). However, the second model has less practical significance and it is hard to use this model to guide a prospective fitness-watch wearer on what small goals to achieve in terms of minutes active and steps walked. On the contrary, the first model runs into issues of multicollinearity but knowing that total distance and total steps are the highest contributors to our outcome variable is something that can be tracked by most watches and can be easily analyzed.

2. The third model also explores the ensemble regression, a model that combines different kinds of models together, including four linear models - lasso, lasso lars, elastic net and ridge, along with two tree based models - XGBoost and GBoost. This model contains a RMSE of 0.24 and a R-squared of 0.53, which is high enough given the fact that multiple models were incorporated. 

## Applications

To further improve the accuracy of our model, my group would like to explore other non-linear regression models as well as to connect with APIs to access large, more robust database. Our project can contribute meaningful insight for research studies on the effectiveness of calorie consumption in weight loss, Calorie Tracking Apps like Myfitnesspal, and Fitness & Nutrition programs. Lastly, we hope to enhance the awareness of taking care of our physical and mental health by cultivating a healthy and balanced lifestyle. 






