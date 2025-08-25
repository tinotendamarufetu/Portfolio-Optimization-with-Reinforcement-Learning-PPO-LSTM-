Portfolio Optimization with Reinforcement Learning
PPO + LSTM | Custom Gym Environment | Trading Constraints

**📌 Project Overview**
This project explores portfolio optimization using reinforcement learning (RL). We design a custom multi-asset trading environment (PortfolioEnvV2) and train a Proximal Policy Optimization (PPO) agent with LSTM memory to capture temporal dependencies in financial markets.

The framework simulates daily trading decisions across a broad set of ETFs and assets, applying realistic constraints such as commissions, slippage, maximum exposure per asset, and anti-overtrading rules.


**⚙️ Key Features**

Custom Gymnasium Environment (PortfolioEnvV2)
  - Multi-asset OHLCV inputs
  - Transaction costs, slippage, and taxes
  - Anti-overtrading controls (cooldowns, turnover penalty, trade caps)
  - Reward shaped by profitability, drawdowns, and trading discipline
  
Reinforcement Learning Agent
  - PPO with LSTM (from sb3-contrib)
  - Tuned hyperparameters for stable training
  - Handles temporal credit assignment and non-stationary dynamics

Evaluation & Benchmarking
  - Train vs Test performance comparison
  - Equal-weighted buy-and-hold benchmark
  - Metrics: CAGR, Sharpe Ratio, Max Drawdown, Final NAV
  - Rich visualizations: NAV curves, rolling Sharpe, drawdowns, reward trends


📊 Results
RL Agent Performance:

Train:
  - Final NAV: 55,629
  - CAGR: 6.41%
  - Sharpe: 0.64
  - Max Drawdown: -26.55%
  - Trades: ~957 (~2/day)

<img width="3571" height="3178" alt="image" src="https://github.com/user-attachments/assets/51e10761-43c4-41ea-b8a9-ab2b6919e61b" />

Test:
  - Final NAV: 25,084
  - CAGR: 5.65%
  - Sharpe: 0.60
  - Max Drawdown: -17.43%
  - Trades: ~353 (~2/day)

<img width="3578" height="3178" alt="image" src="https://github.com/user-attachments/assets/8277da2c-f56e-49fb-abec-0dbbda9be4e5" />


📌 Compared to the equal-weighted buy & hold baseline, the RL agent achieves similar returns but with reduced drawdowns and controlled trading frequency.


🔮 Next Steps
  - Feature engineering: volatility, momentum, macroeconomic indicators
  - Hyperparameter sweeps for PPO
  - Comparison with other RL algorithms (DDPG, SAC)
  - Deployment as a live trading simulation or backtesting framework

👉 This project demonstrates the feasibility of RL for systematic trading, balancing profitability and risk while avoiding overtrading.
