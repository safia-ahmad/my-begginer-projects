# my-begginer-projects
just some projects(simple to medium) i did for practicing ml

hey everyone
lemme teach u some of the basics of simple linear reg.(closed form solution)
########################################################################################################################
q1. what is simple linear reg and why is it used?
Simple Linear Regression is a method used to understand the relationship between two things:

One independent variable (the input or cause, like hours studied),
and one dependent variable (the output or result, like exam score).
It tries to fit a straight line through the data points that best shows how one affects the other.

example:
Imagine you want to predict someone's exam score based on how many hours they studied.
You collect data from a few students and plot it on a graph. Simple linear regression draws a best-fit straight line through that data. With that line, you can predict what exam score someone might get if they study, say, 6 hours.

Why is it used?
To predict: You can guess unknown outcomes (like future sales, scores, etc.).
To understand relationships: Like knowing if more studying really leads to higher scores.
To find trends: It shows the general direction of the data.
##########################################################################################################################
q2.what is the basic maths and formulas used in simple linear reg?
Simple Linear Regression tries to fit a straight line:
**y=mx+c** 
Where:
y = predicted value (output)
x = input (independent variable)
m = slope (how much y changes when x increases)
b = intercept (value of y when x = 0)
E(m,b)=∑ i-1 to n (Yi-mxi-b)^2  --> so only m and b ki wajah se eqn minimize krsakte hai

formulas of m and b:
1)m=∑(xi-x̄)(Yi-Ȳ)/∑(xi-x̄)^2 
2)b=Ȳ-mx̄
where Ȳ,x̄ are the means respectively
##########################################################################################################################
q3.How Do We Find Best Parameters?
In Simple Linear Regression, if you're using the closed-form solution, you can directly compute the best parameters — the slope 
m and intercept b — using just the formulas.
##########################################################################################################################
FULL WORKFLOW OF A SIMPLE LINEAR REGRESSION CODE:
STEP 1: Import Libraries
STEP 2: Load the Dataset
STEP 3: Understand the Data 
STEP 4: Visualize the Data
Use plots to check if a linear relationship exists
STEP 5: Prepare the Data
Choose:
X → independent variable (input)
y → dependent variable (output/target)
Then split into train and test
STEP 6: Train the Model
(make an object of linear regression class and fit kro x and Y)
STEP 7: Make Predictions
y_pred = model.predict(X_test)

You can also predict on any new data:
model.predict([[7.5]])  # If 7.5 is the new input
STEP 8: Evaluate the Model(using regression metrics)
Low MSE and R² close to 1 means a good model.
STEP 9: Visualize the Model’s Fit
STEP 10: Interpret the Model
STEP 11: Add User Input (Optional)
##############################################################################################################################
q4.What does the slope (m) mean?
The slope tells you how much y will change when x increases by 1.
🔸 Simple interpretation:
If m = 2: every time x goes up by 1, y increases by 2
If m = -3: every time x goes up by 1, y decreases by 3
It shows the rate of change between x and y.

🧃 Example:
You're predicting test score based on hours studied:
Score
=5*Hours+10
Score=5⋅Hours+10
Here, slope = 5, meaning:
Every extra hour of study increases the score by 5 points (on average)
##############################################################################################################################
q5. What does the intercept (b) mean?
The intercept is the predicted value of y when x = 0.
in the eqn ŷ = mx + b
if x=0, then ŷ=b
🧃 Example:
From above:
Score=5*Hours+10
Score=5⋅Hours+10
If someone studies for 0 hours, their predicted score is 10.
So here:
b = 10 = base value (or starting point) when no input is given.
###############################################################################################################################
📊 Regression Metrics:
1)Mean Absolute Error (MAE): On average, how much are the predictions off — treats all errors equally.
MAE = (1/n) × Σ |yᵢ - ŷᵢ|

2)Mean Squared Error (MSE):Average of squared errors — bigger errors are punished more.
MSE = (1/n) × Σ (yᵢ - ŷᵢ)²

3)Root Mean Squared Error (RMSE):Square root of MSE — brings the error back to the original scale.
RMSE = √[ (1/n) × Σ (yᵢ - ŷᵢ)² ]

4) R-squared (R² Score): Tells how well the model explains the variance in the target variable.
Ranges from 0 to 1 (or can be negative if the model is very bad).
R² = 1 - [ Σ (yᵢ - ŷᵢ)² / Σ (yᵢ - ȳ)² ]
Where:

yᵢ = actual value
ŷᵢ = predicted value
ȳ = mean of actual values
n = number of data points
###############################################################################################################################
q6. when to use which regression metric?
🔹 MAE (Mean Absolute Error)
Use this when you want a simple, average error.
It tells you how much your predictions are off — on average — no matter if the error is big or small.
✅ Use MAE if you care equally about all errors and want an easy-to-understand number.

🔹 MSE (Mean Squared Error)
Use this when you want to punish big errors more.
It squares the errors, so large mistakes count a lot more.
✅ Use MSE if big errors are very bad in your problem (like medical or finance predictions).

🔹 RMSE (Root Mean Squared Error)
Use this when you want the same effect as MSE but in the original unit of your output.
It’s just the square root of MSE.
✅ Use RMSE if you want to penalize big errors and still get the result in a readable scale (like dollars, marks, kg, etc.).

🔹 R² Score (R-squared)
Use this to understand how good your model is overall.
It tells you how much of the variation in y is explained by x.
✅ Use R² to check if your model is actually useful (closer to 1 = better).
#######################################################################################################################################
Linear Regression main functions in scikit-learn:
1)fit(X, y)
What it does: Trains the linear regression model on your data.
Inputs:
X: Feature data (independent variables) — usually a 2D array or DataFrame.
y: Target data (dependent variable) — 1D array or Series.
Output: It learns the best-fit line (coefficients and intercept) from the data.
example:model.fit(X_train, y_train)

2)predict(X)
What it does: Uses the trained model to predict target values for new input data X.
Inputs:
X: New feature data.
Output: Predicted target values array.
example:y_pred = model.predict(X_test)
score(X, y)

3)score(X, y)
What it does: Returns the coefficient of determination R^2 of the prediction.
Inputs:
X: Feature data.
y: True target values
example: accuracy = model.score(X_test, y_test)

Attributes (not functions, but important):
coef_
After .fit(), contains the learned slope(s) or coefficients (weights) for each feature.
Example:
print(model.coef_)
intercept_

The learned intercept (bias) term of the model after fitting.
Example:
print(model.intercept_)

####################################################################################################################################

