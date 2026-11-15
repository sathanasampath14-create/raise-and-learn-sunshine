# 🌻 Raise and Learn, Sunshine

**Authors:** Sathana S (EC24b1129) and Mohitha S (EC24I1017)
**Course:** Introduction to Data Science, Part B (game for learning data science concepts)
**Play it here:** (https://sathanasampath14-create.github.io/raise-and-learn-sunshine/)
A retro "90s homepage" garden game with two mini-games. You learn by experimenting, not by reading: you change a setting, see what happens, and discover the rule yourself. The game is a single file (`index.html`) with no installation and no external libraries.

## The two games

| Game | Concepts | What the player does |
|---|---|---|
| **1. Predict the Bloom** | Overfitting, underfitting, bias-variance trade-off, why we test on unseen data | Fits a growth curve to 12 measured sunflowers using a complexity slider, tests it on hidden new sunflowers (only 5 tests), then locks in a model |
| **2. Sample the Field** | Sampling, sampling bias, effect of sample size | Chooses where to sample (random, roadside, shady back) and how many plants (150-plant budget) to estimate a field's average height |

## Learning objectives
**Game 1.** After playing, you can: (1) explain that training error keeps falling as a model gets more complex; (2) explain that error on new data falls and then rises again; (3) name underfitting (high bias) and overfitting (high variance); (4) say why we test on unseen data.

**Game 2.** After playing, you can: (1) explain that a sample should represent the whole population; (2) explain that a biased method stays wrong however large the sample; (3) explain that random samples get less noisy as they get larger; (4) estimate a population mean from a sample.

## How to play
1. Open the game and choose **Game 1** or **Game 2** (the **How to Play** page has the full instructions).
2. Answer the quick *before you play* question.
3. **Game 1:** move the **complexity** slider (the red curve is a polynomial fitted by least squares to the yellow dots). Press **Test on new sunflowers** to measure it on 300 hidden plants (5 tests; re-testing a complexity you already tried is free). Press **Lock in** when ready. Within 3% of the best possible error earns 3 stars.
4. **Game 2:** choose the sampling method and number of plants, press **Measure sample**, compare estimates, and press **Use as final** on the one you trust. The game then repeats your method 300 times to reveal its bias and spread. Under 3 cm error earns 3 stars.
5. Answer the *after you play* question and compare.

## How the game works (real computation, nothing hard-coded)
- A fresh random garden is generated every time (seeded pseudo-random numbers with Gaussian noise around a hidden true curve).
- Game 1 fits a polynomial of the chosen degree by **least squares** (normal equations solved with Gauss-Jordan elimination) and computes real RMSE on the training dots and on 300 hidden test plants. The "best possible complexity" is found by measuring every degree from 1 to 9.
- Game 2 simulates a 400-plant field whose height depends on the row (roadside plants are taller, shady back rows shorter), draws real samples without replacement, and runs a 300-repeat simulation of the player's method to show bias and noise.

## Evidence of learning (playtest)
The **Playtest** page records, for each tester: a before/after prediction on a true/false statement ("A more complex model ALWAYS predicts brand-new data better" and the sampling statement), a rating, whether they discovered the idea, what they learned in their own words, and what confused them. **Export CSV** downloads everything, including the before and after answers.

## Run locally
Download `index.html` and double-click it. No server or installation is needed.
