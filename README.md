# FIFA-WC26-predictor-
I Built a fully offline FIFA World Cup 2026 prediction engine — using Elo ratings, Poisson goal modeling, and Monte Carlo simulation.

The idea: skip live APIs and dependency on internet access entirely. Instead, I built a self-contained simulator that:
-Assigns every one of the 48 qualified teams an Elo strength rating
-Uses a Poisson distribution to convert Elo gaps into realistic, randomized scorelines for every match
 -Simulates the full tournament — all 12 groups, Round of 32 through the Final — 10,000 times over via Monte Carlo simulation. 
-Outputs win probabilities for every team, plus a visual bracket showing one full simulated run, group stage to champion

No backend, no API calls, no server. Pure JavaScript running client-side — built specifically to work without any internet connection.
A fun exercise in applying real statistical modelling (the same techniques used by professional sports analytics) to a project I could build, test, and run entirely on my own terms.

How it works:
1) Every one of the 48 qualified teams gets an Elo rating — a single number representing historical strength
2) When two teams meet, the Elo gap converts into "expected goals" for each side
3) A Poisson distribution turns that expectation into a real scoreline — so upsets can still happen, just less often for big mismatches
4) One full tournament is simulated end-to-end — all 12 groups, Round of 32 through the Final
5) Then the entire tournament is replayed 10,000 times (Monte Carlo simulation)
6) The system counts how often each team wins across all 10,000 runs → a real win probability, for every team.
