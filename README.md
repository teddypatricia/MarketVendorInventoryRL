# Market Vendor Inventory Control with Reinforcement Learning

## Overview
This project uses a **Q-learning RL agent** to help a market vendor optimize daily stock orders, maximizing profit while minimizing stockouts and holding costs.

- **State:** `(stock, day_of_week, moving_average_demand)`
- **Action:** Order quantity (0–20)
- **Reward:** Daily profit = revenue − ordering cost − holding cost − stockout penalty

## Folder Structure
market-inventory-rl/
├─ app.py # FastAPI API
├─ env.py # Market environment
├─ q_learning.py # RL training
├─ train_and_eval.py # Evaluation
├─ api_demo.py # Demo API calls
├─ requirements.txt # Dependencies
├─ Dockerfile # Container setup
├─ models/q_table.pkl
├─ presentation/ # Slides

## Usage
1. **Install dependencies:**
python -m venv venv
.\venv\Scripts\activate
pip install -r requirements.txt

Run API
uvicorn app:app --reload --port 8080

Test examples:
python api_demo.py

Expected outputs:
Example 1 → 7
Example 2 → 11
Example 3 → 0

Evaluate RL agent:
python train_and_eval.py
Shows average daily profit, profit std, and stockouts

Notes
Keep the q_table.pkl to match presentation results.
