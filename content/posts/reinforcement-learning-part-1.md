+++
title = 'Reinforcement Learning Part 1'
date = 2024-08-21T22:00:42+02:00
draft = true
+++

## The goal

Developing a small app that leverages reinforcement learning was one of my 2025 NY resolutions. Lacking a motivating, I dragged this project. Every now and then I play this farming rpg called stardew valley. It contains a fishing minigame, see details in the official documentation. The goal of the game is to . Upon doing a quick online search, I could not find a satisfactory program and decided to give it a try. In this series I want to document my progress on the goal to autmate the fishing minigame with an AI assistant that learns to fish leveraging reinforcement learning.

## Part 1 - Goal definition and initial exploration

[GitHub repository](https://github.com/rico-schmidt/stardew-fishing)

### Goal

* no automated fish rod throwing
* AI assistant starts when fishing screen appears
* 

### Anticipated difficulties

* overlay might interfere with fishing game screen (see e.g. screenshot)
* how to detect success, especially perfect catch

### Limitations

* No bobbers
* No legendary fish
* No min-maxing on frame usage


### subgoal 1 - detect game start and end

* game start: scan every x frames, look out for fishing bar template
* sleep has disadvantage that not every x frames but x frames + code execution duration is checked
* game end: if no bar detection inside minigame, declare game end
* reward collection
* * test wait x frames for fish to show up
* * if treasure was detected during minigame: treasure reward if treasure vanishes during game and fish shows up
* * template match for perfect catch? maybe alternative goal: max time 20s, give more points the faster 
* * if no fish shows up -> failed, minus reward
* treasure chest appears 1-3s after game start

### subgoal 2 - detect rewards (fish, treasure, perfect catch)