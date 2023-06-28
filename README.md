# catan-analysis

Analysis of Initial Settlers of Catan settlement placement on final victory points (VP). `catan.ipynb` contains analysis.

## Background

In Settlers of Catan, the game begins by each player taking turns placing their first 2 settlements. This has a significant effect on how the rest of the game plays out. The purpose of this analysis was to map the quality of those placements to the final point total, which is a proxy for likelihood to win.

## Dataset

Source: <https://www.kaggle.com/datasets/lumins/settlers-of-catan-games>

Data collected by an avid Catan player of 50 games, each with 4 players. One row per player-game, collecting (among other things) the location of each of the first 2 settlements and the final point total.

## Methods

The following procedure was followed:

1. Calculate total "pips" by resource for each players starting settlement. Pips denote how likely a number is to be rolled, corresponding to the number of expected rolls per 36 dice rolls.
2. Add many rows with 0 pips for every resource and a final score of 0.
3. Use an [Explainable Boosting Machine](https://interpret.ml/docs/ebm.html) to estimate the final VPs as an additive nonlinear function of pips per resource, as well as a flag for if the player was the dataset collector, who is an above average player.
4. Plot the estimated VPs per pips per resource together

To complete the visualization, I added finishing touches, such as the resource pictures on the lines, a visual explanation of pips, and a made-up quote for fun :).
