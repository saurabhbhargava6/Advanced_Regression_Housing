# Advanced_Regression_SurpriseHousing
> A US-based housing company named Surprise Housing has decided to enter the Australian market. The company uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price. For the same purpose, the company has collected a data set from the sale of houses in Australia. The data is provided in the CSV file below.
 
## Table of Contents
* [Problem Statement](#problem-statement)
* [General Info](#general-information)
* [Conclusions](#conclusions)
* [Technologies Used](#technologies-used)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## Problem Statement

### Business Understanding

The company is looking at prospective properties to buy to enter the market. You are required to build a regression model using regularisation in order to predict the actual value of the prospective properties and decide whether to invest in them or not.

### Business Goal:

You are required to model the price of houses with the available independent variables. This model will then be used by the management to understand how exactly the prices vary with the variables. They can accordingly manipulate the strategy of the firm and concentrate on areas that will yield high returns. Further, the model will be a good way for management to understand the pricing dynamics of a new market.

### Business Risk:

- Predicting a higher sale price for a house would not attact the customers which would lead to a loss to the company
- Predicting a lower sale price for a house would lead to reduces profit margin for the company

### Requirement:

- Which variable are significant in predicting the sale price of the house?
- How well those variabe describe the sale price of the house?
- Optimal value of lambda for ridge and lasso regression?

## General Information
- Steps for crreating a Regularized regression model :
<ol>
    <li>Data Visualization</li>
      <ol>
        <li>Perform EDA to understand various variables.</li>
        <li>Check the correlation between the variables.</li>
      </ol>
    <li>Data Preparation</li>
      <ol>
        <li>Create dummy variables for all the categorical features.</li>
        <li>Divide the data to train & Test.</li>
        <li>Perform Scaling.</li>
        <li>Divide data into dependent & Independent variables.</li>
      </ol>
    <li>Data Modelling & Evaluation</li>
      <ol>
        <li>Create Linear Regression model using RFE</li>
        <li>Create L1 and L2 Regularized Models using the output of the RFE</li>
        <li>Check the various assumptions.</li>
        <li>Check the Adjusted R-Square for both train & Test data.</li>
        <li>Report the final model.</li>
      </ol>
</ol>
- Data Set : train.csv 

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
<div class="alert alert-block alert-danger">
    <span style='font-family:Georgia'>
        <b>EDA on Continuous Variable: </b>
        <ol>
            <li>LotFrontage - As LotFrontage in increases from <b>[20.7 to 196.2]</b> the SalePrice increases</li>
            <li>LotArea - As LotArea in increases from <b>[1086 to 65483]</b> the SalePrice increases</li>
            <li>MasVnrArea - As MasVnrArea in increases from <b>[0 to 1280]</b> the SalePrice increases</li>
            <li>BsmtFinSF1 - As BsmtFinSF1 in increases from <b>[0 to 2257]</b> the SalePrice increases</li>
            <li>BsmtFinSF2 - As BsmtFinSF2 in increases thier is not much effect on SalePrice</li>
            <li>BsmtUnfSF - As BsmtUnfSF in increases from <b>[1168 to 2336]</b> the SalePrice increases</li>
            <li>TotalBsmtSF - As TotalBsmtSF in increases from <b>[0 to 3666]</b> the SalePrice increases</li>
            <li>1stFlrSF - As 1stFlrSF in increases from <b>[329.64 to 3384]</b> the SalePrice increases</li>
            <li>2ndFlrSF - As 2ndFlrSF in increases from <b>[206.5 to 1858]</b> the SalePrice increases</li>
            <li>GrLivArea - As GrLivArea in increases from <b>[328 to 4480]</b> the SalePrice increases</li>
            <li>GarageYrBlt - As GarageYrBlt in increases thier is not much effect on SalePrice</li>
            <li>GarageArea - As GarageArea in increases from <b>[0 to 1276]</b> the SalePrice increases</li>
            <li>WoodDeckSF - As WoodDeckSF in increases from <b>[0 to 685]</b> the SalePrice increases</li>
            <li>OpenPorchSF - As OpenPorchSF in increases thier is not much effect on SalePrice</li>
            <li>EnclosedPorch - As EnclosedPorch in increases thier is not much effect on SalePrice</li>
            <li>AgeBuilt - As AgeBuilt in increases from <b>[0 to 81]</b> the SalePrice decreases and from <b>[81 to 136]</b> the SalePrice slightly increases</li>
            <li>AgeRemod - As AgeRemod in increases from <b>[0 to 60]</b> the SalePrice decreases</li>
        </ol>
        <b>EDA on Categorical Variable: </b>
        <ol>
            <li>MSSubClass - 20, 50, 75, 120 have higher SalePrice than other MSSubClass</li>
            <li>MSZoning - RL and FV have higher SalePrice than other MSZoning</li>
            <li>LotShape - IR2 and IR1 have slightly higher avarage SalesPrice than other LotShape</li>
            <li>LandContour - HLS has slightly higher avarage SalesPrice than other LandContour</li>
            <li>LotConfig - CulDSac has slightly higher avarage SalesPrice than other LotConfig</li>
            <li>Neighborhood - NoRidge, NridgHt, Timber and StoneBr have higher SalePrice than other Neighborhood</li>
            <li>Condiction1 - PosN and RRNn have slightly higher SalePrice than other Condiction1</li>
            <li>BldgType - 1Fam and TwnhsE have slightly higher SalePrice than other BldgType</li>
            <li>HouseStyle - 2Story, 1Story and 2.5Fin have higher SalePrice than other HouseStyle</li>
            <li>OverallQual - As the OverallQual increases the the SalePrice increases steeply</li>
            <li>OverallCond - As the OverallCond increases the the SalePrice increases</li>
            <li>RoofStyle - No effect of RoofStyle on the SalePrice</li>
            <li>Exterior1st - VinylSd, CemntBd and Stone have higher SalePrice than other Exterior1st</li>
            <li>Exterior2nd - VinylSd, CemntBd and ImStucc have higher SalePrice than other Exterior2nd</li>
            <li>MasVnrType - Stone and SBrkr have higher avarage SalesPrice than other MasVnrType</li>
            <li>ExterQual - Ex has significant higher SalePrice than other ExterQual</li>
            <li>ExterCond - No effect of ExterCond on the SalePrice</li>
            <li>Foundation - PConc has higher avarage SalesPrice than other Foundation</li>
            <li>BsmtQual - Ex and Gd have significant higher SalePrice than other BsmtQual</li>
            <li>BsmtCond - TA and Gd have higher SalePrice than other BsmtCond</li>
            <li>BsmtExposure - Gd has higher SalePrice than other BsmtExposure</li>
            <li>BsmtFinType1 - GL Q has higher SalePrice than other BsmtFinType1</li>
            <li>BsmtFinType2 - GL Q has higher SalePrice than other BsmtFinType2</li>
            <li>HeatingQC - As HeatingQC becomes poor the SalePrice decreases</li>
            <li>BsmtFullBath - No effect of BsmtFullBath on the SalePrice</li>
            <li>FullBath - 2 and 3 ave significant higher SalePrice than other FullBath</li>
            <li>HalfBath - 1 has slightly higher avarage SalePrice than other HalfBath</li>
            <li>BedroomAbvGr - 0 and 4 have slightly higher avarage SalePrice than other BedroomAbvGr</li>
            <li>KitchenQual - Ex has significant higher SalePrice than other KitchenQual</li>
            <li>TotRmsAbvGrd - As the TotRmsAbvGrd increases the the SalePrice increases</li>
            <li>FirePlaces - As the FirePlaces increases the the SalePrice increases</li>
            <li>FireplaceQu - Ex has significant higher SalePrice than other FireplaceQu</li>
            <li>GarageType - Attchd and BuiltIn have higher SalePrice than other GarageType</li>
            <li>GarageFinish - Fin has higher SalePrice than other GarageFinish</li>
            <li>GarageCars - As the GarageCars increases the the SalePrice increases except for 4</li>
            <li>GarageQual - Gd and Ex have higher SalePrice than other GarageQual</li>
            <li>Fence - No effect of Fence on the SalePrice</li>
            <li>MoSold - No effect of MoSold on the SalePrice</li>
            <li>YrSold - No effect of YrSold on the SalePrice</li>
            <li>SaleType - New, CWD and Con have higher SalePrice than other SaleType</li>
            <li>SaleCondition - Partial has significant higher SalePrice than other SaleCondition</li>
        </ol>
    </span>    
</div>
<p><strong>Which variables are significant in predicting the price of a house?</strong></p>
<ul>
<p><strong>How well those variables describe the price of a house?</strong></p>
<ul>
<div>
<ul>
<li><span style="color: #000000; background-color: #ffffff;">Neighborhood_Crawfor</span></li>
<li><span style="color: #000000; background-color: #ffffff;">GrLivArea</span></li>
<li><span style="color: #000000; background-color: #ffffff;">OverallQual</span></li>
<li><span style="color: #000000; background-color: #ffffff;">SaleCondition_Normal</span></li>
<li><span style="color: #000000; background-color: #ffffff;">SaleCondition_Partial</span></li>
<li><span style="color: #000000; background-color: #ffffff;">Neighborhood_StoneBr</span></li>
<li><span style="color: #000000; background-color: #ffffff;">MSZoning_RL</span></li>
<li><span style="color: #000000; background-color: #ffffff;">MSZoning_FV</span></li>
<li><span style="color: #000000; background-color: #ffffff;">OverallCond</span></li>
<li><span style="color: #000000; background-color: #ffffff;">Condition1_Norm</span></li>
</ul>
</div>
    </ul>
<p><strong>Optimal value of lambda for ridge and lasso regression?</strong></p>
<ul>
<li>Ridge : 10.0</li>
<li>Lasso : 0.001</li>
</ul>

<div class="alert alert-block alert-success">
    <span style='font-family:Georgia'>
        <b>Final Model :</b> 
        <p>Chossing the Lasso Regularized model as the final model to predict the SalePrice because of the following reasons</p>
        <ul>
            <li>More Feature elimination which would lead to making the model simple, robust and generalized model</li>
            <li>Similar performace when compared to Ridge Regularization</li>
        </ul>
    </span>    
</div>

## Technologies Used
- pandas - 2.0.3
- numpy - 1.22.4
- matplotlib - 3.7.1
- seaborn - 0.12.2
- plotly - 5.15.0
- sklearn - 0.23.1
- statsmodel - 0.14.0


<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
- This project was group case study for an online advance course.
- https://www.geeksforgeeks.org/
- https://seaborn.pydata.org/
- https://plotly.com/
- https://pandas.pydata.org/
- https://learn.upgrad.com/


## Contact
Created by [@saurabhbhargava6] - feel free to contact me!


