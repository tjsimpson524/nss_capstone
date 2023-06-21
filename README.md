BEATING THE NBA MONEYLINE MARKET

1. Model & feature selection
2. Calibrate the model
3. K-Fold Cross Validation (10-30 Fold) for optimal wager threshold
4. Model with selected features and wager threshold as a parameter


GOAL

Use NBA betting market data and ML tools to create a model that will outperform NBA moneyline markets. 

DATA

Betting market data for NBA seasons 2007-2022 was used in this project. The data is easily accquired at https://www.sportsbookreviewsonline.com/scoresoddsarchives/nba/nbaoddsarchives.htm

STEPS TAKEN:

1. Import and clean data as needed.

2. Training several models (GRB, XG Boost, Random Forest, Naive Bayes, Decision Tree) on NBA seasons 07-20 with the goal to predict the winners of every game of NBA       season 21-22. The model and features that proved the most predictive was chosen. The best model and feature combination proved to be Gradient Boost with five market    features" Closing Moneyline, Open & Close Spread, Open & Close Total.

3. Ensuring that the Gradient Boost model was properly calibrated, a calibration curve was applied. No tunning necessary.

4. To determine the optimal point at which to wager, K-Fold Cross Validation was applied. Taking he difference between the predicted probabilitites of the                 Gradient Boost model and the implied probabilitites of the closing moneylines for the NBA season of 07-20, provided thresholds for investigation. Adding to this was    the payout for wagers at each threshold point. All wagers were hypothetical and a flat $100, regardless. Averaging up the most profitable threshold over all folds      was carried over to the next step.

5. Returning to the original Gradient Boost model and applying the threshold parameter given by the K-Fold CV, the model was rerun, only wagering on games in which        those differences between the Gradient Boost's predicted probabilities and the implied probabilitites of the closing moneyline fell within the specified threshold.

Analysis:

A 10,20,30 Fold version of K-Fold CV was executed. Despite all fold evaluations showing profitability with the training set, only the thresholds suggested by the 20 and 30 fold versions proved profitable. 'Profitable' in the sense that, had the model been used to actually wager on the NBA 21-22 season, the final result would have been a gain in bankroll, though the gains would be small in comparison to the cost. 

For example, the 30 fold recommends a wager threshold of .021. Using this to wager on the 21-22 season proved profitable to a little over $570. However, the cost was well over $40,000 to attain that small profit.


Future Improvements:

Though the model proved profitable, the cost to attain that profitability was less the satisfactory. These are a few of the improvements -- ones I intend to try in the near future -- that could prove to bridge the gap between cost and profit.

1. The model was placing wagers vs the most efficient line of the day -- the closing line. Testing the model against softer lines (openers, midday, etc) could improve     results.

2. Adjusting wager based on the size of the difference between the model's predicted probabilitites and the implied probabilitites of the moneyline. Larger gaps would recieved larger wagers, and vice versa.

3. There were only five features used in this model. Adding other market features such as opening moneyline, first half winner, etc, may also help improve results.  
