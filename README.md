<h1 align="center">💹 Quant Portfolio Simulator</h1>

<p align="center">
  <b>Simulate and backtest trading strategies with real risk controls</b><br/>
  Analyze portfolios with interactive charts and institutional-grade analytics.
</p>

<p align="center">
  <a href="https://quant-portfolio-simulator-7bo0l1l7r-sankets-projects-8fae85e1.vercel.app/" target="_blank">
    <img src="https://img.shields.io/badge/Live-Vercel-%23000000?style=for-the-badge&logo=vercel" />
  </a>
  <a href="https://github.com/sanketk77/quant-portfolio-simulator">
    <img src="https://img.shields.io/github/stars/sanketk77/quant-portfolio-simulator?style=for-the-badge" />
  </a>
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge" />
</p>


A cutting-edge, interactive portfolio backtesting tool built with ⚛️ React, 🟦 TypeScript, and 🎨 Tailwind CSS — designed for quants, traders, and analysts to simulate multi-asset strategies with real-time risk management and professional analytics.

🌟 Key Highlights
📂 Portfolio Management
💼 Multi-Asset Simulation: Supports equities (AAPL, MSFT, GOOGL) and cryptocurrencies (BTC, ETH)

⏳ Custom Timeframes: Choose your own backtesting range

💵 Capital Allocation: Set initial capital and configure dynamic sizing

📈 Strategy Engine
⚖️ Equal Weighting: Simple diversification through periodic balancing

🚀 Momentum: Ride trends by buying strength and exiting weakness

🔄 Mean Reversion: Exploit volatility by buying dips and selling peaks

🛡️ Risk Management Layer
⛔ Stop Loss: Exit positions to protect capital

📉 Max Drawdown: Trigger portfolio liquidation upon breaching loss limits

🌪️ Volatility Cap: Automatically adjust exposure in turbulent markets

📊 Interactive Analytics
📈 Real-time Charts: Visualize NAV, drawdown, and returns live

📋 Trade Logs: Exportable, sortable, and filterable transaction data

📌 Performance Metrics: Track Sharpe ratio, alpha/beta, win rate, max drawdown

🛠️ Built With
🔧 Tech	🔍 Role
⚛️ React 18	UI and component framework
🟦 TypeScript	Static typing and better dev tooling
🎨 Tailwind CSS	Fast, utility-first styling
📊 Recharts	Beautiful financial data visualizations
🧠 Lucide Icons	Modern, lightweight icon set
⚡ Vite	Ultra-fast dev server and build tool
📅 date-fns	Efficient date manipulation utilities
## 📁 Project Structure

```
src/
├── components/          # Reusable UI components
│   ├── AssetInput.tsx      # Ticker input and portfolio configuration
│   ├── StrategySelector.tsx # Trading strategy selection
│   ├── RiskControls.tsx    # Risk management parameters
│   ├── PortfolioChart.tsx  # Interactive performance charts
│   ├── TradeLog.tsx        # Trade history table
│   └── MetricsDashboard.tsx # Performance metrics display
├── hooks/               # Custom React hooks
│   └── useSimulation.ts    # Simulation state management
├── services/            # Data and business logic
│   ├── yfinance.ts         # Mock financial data service
│   └── simulation.ts       # Portfolio simulation engine
├── types/               # TypeScript interfaces
│   └── index.ts            # Core type definitions
├── utils/               # Helper functions
│   └── calculations.ts     # Financial calculations
└── App.tsx              # Main application component
```

## 🚀 Getting Started

### Prerequisites

- Node.js 16+
- npm or yarn

### Installation

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd quant-portfolio-simulator
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Start development server**

   ```bash
   npm run dev
   ```

4. **Open in browser**
   Navigate to `http://localhost:5173`

### Building for Production

```bash
npm run build
npm run preview
```

## 📊 Usage Guide

### 1. Portfolio Configuration

- **Add Assets**: Enter ticker symbols (AAPL, MSFT, BTC, etc.)
- **Set Timeframe**: Choose start and end dates for backtesting
- **Initial Capital**: Set starting portfolio value ($1,000 - $10,000,000)

### 2. Strategy Selection

- **Equal Weight**: Best for diversified, low-maintenance portfolios
- **Momentum**: Suitable for trending markets and growth-focused strategies
- **Mean Reversion**: Effective in ranging markets with high volatility

### 3. Risk Management

- **Max Drawdown (5-50%)**: Portfolio liquidation trigger
- **Volatility Cap (10-100%)**: Position sizing adjustment threshold
- **Stop Loss (5-50%)**: Absolute loss limit from initial capital

### 4. Running Simulations

- Click "Run Simulation" to start backtesting
- Monitor real-time progress and results
- Export trade history as CSV for external analysis

## 🔧 Customization

### Adding New Assets

Update `src/services/yfinance.ts`:

```typescript
const MOCK_ASSETS: Record<string, Asset> = {
  YOUR_TICKER: {
    ticker: "YOUR_TICKER",
    name: "Your Asset Name",
    price: 100.0,
    change: 1.5,
    changePercent: 1.52,
  },
  // ... existing assets
};
```

### Creating Custom Strategies

Extend `src/services/simulation.ts`:

```typescript
case 'your-strategy':
  // Implement your trading logic
  for (const ticker of this.config.tickers) {
    // Generate buy/sell signals
    signals.push({
      ticker,
      action: 'BUY' | 'SELL',
      weight: 0.2,
      reason: 'Your strategy reason'
    });
  }
  break;
```

### Integrating Real Data

Replace mock service in `src/services/yfinance.ts` with actual API calls:

```typescript
export async function fetchHistoricalData(
  ticker: string,
  startDate: string,
  endDate: string
): Promise<HistoricalPrice[]> {
  // Replace with real API integration
  const response = await fetch(`your-api-endpoint/${ticker}`);
  return await response.json();
}
```

## 📈 Performance Metrics

- **Total Return**: Overall portfolio performance percentage
- **Sharpe Ratio**: Risk-adjusted returns measurement
- **Maximum Drawdown**: Largest peak-to-trough decline
- **Win Rate**: Percentage of profitable trades
- **Volatility**: Annualized price volatility
- **Alpha**: Excess return versus benchmark
- **Beta**: Portfolio correlation with market

## 🔒 Risk Management

The simulator implements multiple layers of risk control:

1. **Position Sizing**: Automatic adjustment based on volatility
2. **Drawdown Protection**: Portfolio liquidation triggers
3. **Stop Loss Orders**: Individual position protection
4. **Correlation Analysis**: Portfolio diversification monitoring

## 🚀 Deployment

### Vercel

1. Connect your GitHub repository
2. Deploy with default settings
3. Environment variables (if needed): None for mock data

### Netlify

1. Build command: `npm run build`
2. Publish directory: `dist`
3. Deploy from GitHub or drag-and-drop

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## ⚠️ Disclaimer

This simulator is for educational and research purposes only. Past performance does not guarantee future results. Always consult with financial professionals before making investment decisions.

## 🔮 Future Enhancements

- [ ] Real-time data integration
- [ ] Machine learning strategy optimization
- [ ] Options and derivatives support
- [ ] Portfolio optimization algorithms
- [ ] Advanced risk metrics (VaR, CVaR)
- [ ] Multi-timeframe analysis
- [ ] Backtesting API for external integration

---
