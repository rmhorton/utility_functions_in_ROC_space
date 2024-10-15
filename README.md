
# Utility Functions in ROC space

### Estimating the value of information provided by an ML classifier

Most ML models do not give you definitive answers, but they can help you to make better guesses. For classifiers, we typically characterize their performance in terms of a quantity vs. quality tradeoff; if you want to discover more true positives, you will need to accept the possibility of more false positives. A Receiver Operating Characteristic (ROC) curve plots true positive rate (also known as 'sensitivity' or 'recall') against false positive rate (1 - the true negative rate, also known as 'specificity').

Here we show two approaches to estimating the business value of a test with a given sensitivity and specificity:

## Linear Value Function

This is a shiny app to explore how utility functions can be used together with an ROC curve to find the decision threshold that maximizes net profit (or, more generally, utility). It was inspored by the blog post "[Machine Learning meets Economics](http://blog.mldb.ai/blog/posts/2016/01/ml-meets-economics/}" by Nicolas Kruchten.

This approach uses a simple linear combination of values for the four cases in a binary confusion matrix (true positives, false positives, false negatives, and true negatives), plus the overall prevalence (or prior probability) of positive cases. This lets us assign a value to any point in the plane on which an ROC curve is plotted. The optimal score threshold for deciding when a case should be considered positive is selected based on the point on the ROC curve that has the highest payoff. The Shiny app (also available at [shinyapps.io](https://ml4managers.shinyapps.io/ML_utility/)) lets you experiment with these parameters.

## Decision Analysis

A more sophisticated utility model can be based on decision anaylysis as described in [Foundations of Decision Analysis](https://www.amazon.com/Foundations-Decision-Analysis-Global-Howard/dp/129207969X).
