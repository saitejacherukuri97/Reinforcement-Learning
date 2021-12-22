# Reinforcement-Learning
This project is part of CSE 574 - Introduction to Machine Learning

**Project Overview:**

The goal of the project is to learn the trends in stock price and perform a series of trades 
over a period of time and end with a profit. In each trade we can either buy/sell/hold. We
will start with an investment capital of $100,000 and the performance is measured as a 
percentage of the return on investment. We will use the Q-Learning algorithm for 
reinforcement learning to train an agent to learn the trends in stock price and perform a 
series of trades.

**Dataset:**

We are given a dataset on the historical stock price for Nvidia for the last 5 years. The 
dataset has 1258 entries starting 10/27/2016 to 10/26/2021. The features include 
information such as the price at which the stock opened, the intraday high and low, the 
price at which the stock closed, the adjusted closing price and the volume of shares traded 
for the day.
Below is the representation of some data from NVDA historical stock price dataset:

![image](https://user-images.githubusercontent.com/42407754/147024623-8aafa1ed-afae-4948-8951-dd6ee1d00ffe.png)

**Python Editor:**
I have used Jupiter Notebook on Google Collab for implementation and shared.

**Environment:**
In Reinforcement learning, Environment is the place which allows Agent to observe State. 
When the Reinforcement Learning agent performs the action, the environment will 
respond to that action and transitions to next state along with providing reward or penalty 
for that action

![image](https://user-images.githubusercontent.com/42407754/147024709-6d0c9c0f-4c5d-4c6b-816a-9e4692ff408e.png)

**Implementing Q-learning:**

**Q-learning algorithm:**

• The goal of the agent is to increase the total rewards it will obtain from the 
environment. This function to maximize is known as discounted return function which 
is given as G.

![image](https://user-images.githubusercontent.com/42407754/147024929-e5658f0a-1efb-4251-a95f-75af4bfe0a84.png)

• For maximizing the rewards, the agent needs to find an optimal policy and this Optimal 
policy is given by Bellman Optimality Equation.

![image](https://user-images.githubusercontent.com/42407754/147024965-64f54b26-2649-46dc-8893-b9e4ca3ce4de.png)

Here Q is **Action-Value** function or **Q-value** function

• α (Alpha) in the equation is the learning rate which controls convergence. It also 
determines how our Q-values are updated.

• γ (gamma) Is the discount factor which determines how much importance we have to 
give to future rewards. A high value for the discount factor will capture long-term 
rewards.

• So, when the agent performs the action, the Q-value of the agent’s current state and 
action is stored in a **Q-table**.

• Q-table is a matrix where we have row for each State and column for each action

**Exploration-Exploitation Trade-off:**

• The agent has no idea about the environment in the beginning, So the agent will need 
to explore the environment rather than to exploit straight away.

• So there’s a need for trade-off between exploration (choosing a random value) and 
exploitation (choosing actions based on Q-values).

• Also, we need to prevent overfitting i.e preventing the agent to take the same route 
always, so we introduce another parameter Epsilon (ϵ) to handle this.

• Instead of always selecting the best values from Q-table, we will sometimes explore 
the action space. 

• This can be achieved by decaying the epsilon value every episode using exponential 
decay formula

![image](https://user-images.githubusercontent.com/42407754/147025042-37272aa4-8561-416f-a507-5a3233ea143c.png)

![image](https://user-images.githubusercontent.com/42407754/147025090-886428b6-7781-4812-ab72-a7a519fe9e4d.png)

![image](https://user-images.githubusercontent.com/42407754/147025107-604b18ae-ff8e-4a26-8587-d8884a35bcae.png)
