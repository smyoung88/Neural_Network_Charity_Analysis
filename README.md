# Neural_Network_Charity_Analysis

## Overview of the Analysis
The purpose of this analysis was to create a machine learning binary classifier that is capable of predicting whether applicants will be successful if funded by a charity. This analysis required implementing a deep learning neural network model.

## Results

### Data Preprocessing 

<b>What variable(s) are considered the target for your model?</b></br>
The target for this model was the "Is-Successful" column which indicates whether or not the investment money was used successfully.

<b>What variable(s) are considered to be the features for your model?</b></br>
The features in this model were the NAME, APPLICATION, TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, INCOME_AMT,SPECIAL_CONSIDERATIONS, STATUS, and ASK_AMT

<b>What variable(s) are neither targets nor features and should be removed from the input data?</b></br>
EIN (Employer identification) was dropped to avoid confusing the model. NAME could have also possibly been dropped, as it was in the original model before optimization, but if new data is entered into the model that carries the same names within the model, it plays a significant role with accuracy.

### Compiling, Training, and Evaluating the Model
  
<b>How many neurons, layers, and activation functions did you select for your neural network model, and why?</b></br> 
In this model, there were three hidden layers with 100, 40, and 10 nodes. Epochs remained the same as the original model, and the activations were 'relu', 'relu', and 'sigmoid', and the output function was 'sigmoid'.

A preview of the code for the model is below:</br>
<img src="https://github.com/smyoung88/Neural_Network_Charity_Analysis/blob/main/Resources/model_optimized.png">

<b>Were you able to achieve the target model performance?</b></br>
Yes

<b>What steps did you take to try and increase model performance?</b></br>
Many different attempts were made to increase the model's performance with very little success. Layers were added, nodes were experimented with, activations were experimented with, both loss and optimizers were changed, and dropping one less column than what was originally dropped. Keeping the NAME column and converting it into data points, had the greatest impact on the model which ultimately increased the accuracy over 75%. It is noted that this could overfit the model to the current dataset, but if any new data is introduced that has names that are already associated with the model, it will be helpful for those scenarios.

## Summary
Overall, increasing the accuracy of the model proved very difficult. All attempts other than adding the NAME column back to the dataset failed at improving the accuracy over 75%. Although adding NAMES back to the dataset, it only increased the model three to four percent to 77.91% and still can be considered useful for applicants that are not already included in the model.

The code output accuracies for both the original and optimized models are shown below:</br>
**Original**</br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Neural_Network_Charity_Analysis/blob/main/Resources/norm_acc.png"></br>
**Optimized**</br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Neural_Network_Charity_Analysis/blob/main/Resources/opt_acc.png">


Another recommended model to solve the classification problem is the Random Forest model since it is known for being good with classification problems. Random Forest may have been a better choice for the initial pass at a model since it can train on a large dataset and predict values in seconds, while the deep learning model required lots of time with trial-and-error. The Random Forest classifier takes less code and has faster performance. Since the dataset is tabular, it is a good place to start.
