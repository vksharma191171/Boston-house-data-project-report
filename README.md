#BOSTON HOUSING DATASET

The Boston housing market is highly competitive(because of the location and for very good facilities), and we wants to work for buisness purpose (be the best real estate agent) in the area. To compete with our idea, we decide to use a  basic Regression techniques concepts to assist us and help out our client with finding the best price for home of there choices(with given factors which he likes the most) . Fortunately, we have the Boston Housing dataset which contains the data on various features for houses in Greater Boston communities, which have MEDV (the median value of homes) for each of those areas which here we have to predict. Our task is to build an optimal model(with good prediction accuracy) based on a statistical analysis with different tools available. This model will finally be used to estimate(predict) the best selling price of houses which help for our clients as per the most important features they want for there house.



*OUR PROJECT STRUCTURE*

1. Introduction and Data description
2. Objective
3. Data pre-processing
4. pre-modelling
     
    (i)  standardise our regressors.
    
    (ii) Splitting Data into Train and Testing set.
    
   (iii) Estimated coefficient, model fitting and RMSE.
   
5. Modelling and Assumption checking
     
    (i)  Leverage and influencial point removal
    
            * Leverage Points
            Diagnostics for Influential points
            * Cook’s Distance
            * DFFITS
            * DFBETAS
            * COVRATIO
            
    (ii) Curvature Checking  and removal.
              
            * APR and CPR
            * Transformation of regressors
            
    (iii) Heteroscedasticity Checking and removal
            
            * Plots of residual vs fiited response
            * Testing of presence of Heteroscedasticity with Breusch Pagan Test
            * Removal
            
    (iv)  Normality Checking and removal
     
            * Checking Through Plots
            * Box-Cox transformation
            * Transformed response and Checking Q-Q plot             
 
 7. Results 
 8. References
 
 
*RESULTS/Conclusions*
 
Our conclusion are as follows:

(1.)  Firstly we fitted data on train set and estimated our RMSE on test set and found RMSE to be 5.9042. 

(2.) Secondly we remove the leverage and influential point from the training data and observed that our RMSE value is decreased after removal of these points and Hence conclude that there is significant effect of ouliers in our model that is previously obtained from training data . Thus , after these diagnosis we found that our model trained has RMSE equal to 5.698279.

(3.) Now , we check whether there is non-linearity of any regressor with respect to residual . We found that "rm" is non-linear with respect to residual and corrected it with the exponential transformation and again find the RMSE value for test data with the help of model trained using training data with transformed "rm" regressor . Finally we found that our RMSE has decreased to 5.128485 which suggest that thier is significant effect of non-linearity of "rm" regressor in the previous model that is trained without transformation of "rm" regressor and Thus after the transformation we have improved the model accuracy .

(4.) After the outlier detection and dealing with non-linearity , Now we checked whether homoscedastic assumption of linear model is satisfied by our model . We performed Breuschpagan test to test for heteroscedasticity and we found that test statistics Q=16.44206 which is greater than the critical value 12.59159. thus we reject homoscedastic assumption for our model and support the claim of hetroscedasticity is present in our model .Now we transformed our model and with the help of iterative method we estimated
our coefficient estimates . Now again we calculated RMSE value on test data set found that there is decrease in RMSE value obtained from previous model and now RMSE is 5.106228 which suggest that there is significant effect of heteroscedasticity in our previous model .

(5.)  Lastly we have validated the normality assumption of response variable with the help of Q-Q plot and we saw that plot does not give us significant evidence of normality of response . Here we use Box-Cox transformation to transform regressor such that normality assumption is satisfied. Again we calculated the RMSE value with transformed regressor and found that RMSE is 5.106228 which is same as previous model and thus we conclude that there is no significant effect of normality of response on the model . Finally after all the diagnosis like oulier detection, dealing with curvature , heteroscedasticity , normality. We get the model as :

MEDV= 5.32655724+(−0.46115639)∗crim+(−0.15854193)∗indus+(−0.17175952)∗nox+ 0.15669411∗transformedrm+ (−0.30314938)∗age+ (−0.517181305)∗dis+(−0.02613209)∗tax+(−0.39179899)∗ptrratio+0.30797729∗black+(−0.83449504)∗lstat

transformedrm=exp(3.0371211)∗exp(0.2978245∗rm)   ,  RMSE for test data = 5.106228. Thus our aim of building a model with good model accuracy and model interpretability is almost achieved . As in predicting "MEDV" RMSE of 5.106228 is considered as small. We have also validated the assumption of linearity , homoscedasticity , normality assumption of General linear model . Now we can predict MEDV(median house price of owner owned house in boston area ) with given feature.  
 
 *SOURCE/CITATION*
1. Lichman, M. (2013). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.
2. James, Gareth, Daniela Witten, Trevor Hastie, and Robert Tibshirani. An Introduction to Statistical Learning: with Applications in R. Springer: 2017.
3. Harrison, D. and D. L. Rubinfeld (1978). Hedonic prices and the demand for clean air. Journal of Environmental Economics and Management, 5, 81-102.
4. introduction to Linear Regression Analysis by Douglas C Montgomery, Elizabeth APeck, G. Geoffrey Vining.
