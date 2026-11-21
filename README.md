# JSE Bridge

> Compare your Jamaican stock portfolio with Canadian and US alternatives, and track it all in one place.

**Status:** Early development (MVP). Features below marked as planned are not built yet.

## What is this?

JSE Bridge is a web app for investors who hold stocks on the Jamaica Stock Exchange (JSE) and want to explore comparable Canadian and US options. You pick the JSE stocks you own, enter your holdings, and the app shows your portfolio in JMD, CAD, or USD, along with similar Canadian/US stocks and ETFs based on sector, size, and risk.

The app compares and informs. It does not execute trades or tell you what to buy.

## Features

### MVP (in progress)
- [ ] Choose from a list of JSE-listed stocks (no manual ticker typing)
- [ ] Enter shares and average cost for each holding
- [ ] Portfolio summary in JMD with a CAD/USD toggle
- [ ] Currency-aware view: live FX rates and the effect of exchange-rate changes
- [ ] Alternative suggestions for each holding:
  - [ ] Match by size and risk (market cap tier, dividend yield, volatility)
  - [ ] ETF alternatives (sector and dividend-focused funds)
- [ ] A short explanation for each suggestion

### Basic stock tracking
- [ ] Watchlist for JSE, TSX, and NYSE/NASDAQ stocks
- [ ] Price and daily change
- [ ] Portfolio gain/loss and allocation chart

### Planned later
- [ ] Historical price charts
- [ ] Price alerts
- [ ] User accounts and saved portfolios (full-stack version with a backend and database)
- [ ] CSV import from brokers

## Data sources

| Data | Source | Notes |
|------|--------|-------|
| JSE prices | Twelve Data (exchange code `XJAM`) | End-of-day only, not real-time |
| Canada/US prices | Twelve Data | Free tier has rate limits |
| FX rates (JMD/CAD/USD) | A free FX API (to be chosen) | |

Notes:
- JSE data is delayed to end-of-day on affordable providers. The official JSE data feeds are paid and aimed at businesses.
- Check your data provider's terms before displaying data publicly. Free tiers are often for personal use only.
- The data layer is meant to be swappable, so the provider can change without rewriting the app.

## Getting started

> Setup steps will be filled in as the project takes shape.

```bash
# Clone the repository
git clone https://github.com/<your-username>/jse-bridge.git
cd jse-bridge

# Install dependencies and start the dev server
# (commands depend on the chosen stack, to be added)
```

### Configuration

You will need API keys, stored in a local `.env` file (never commit this file):

```
TWELVE_DATA_API_KEY=your_key_here
FX_API_KEY=your_key_here
```

## Project structure

> Planned layout, subject to change.

```
jse-bridge/
├── src/
│   ├── components/    # UI components
│   ├── data/          # Data layer (price and FX providers)
│   ├── matching/      # Logic for suggesting alternatives
│   └── pages/         # App screens
├── public/
├── .env.example
└── README.md
```

## Roadmap

1. **Data layer:** JSE stock list, price sources, FX rates
2. **Portfolio entry and summary**
3. **Basic tracking:** watchlist, gain/loss
4. **Matching engine** for Canadian/US stocks and ETFs
5. **Accounts, alerts, and polish**

## Limitations

- Many JSE companies have no close Canadian or US equivalent, so suggestions are approximate. ETFs are often the closer match.
- The app does not account for taxes, brokerage fees, or currency transfer costs.
- It does not connect to a brokerage. Buying foreign stocks requires a broker that allows it.

## Disclaimer

**This app is for educational and informational purposes only. It is not financial, investment, tax, or legal advice.** Suggested alternatives are comparisons based on general characteristics, not recommendations to buy or sell any security. Prices and data may be delayed or inaccurate. Investing involves risk, including loss of principal. Consult a licensed financial advisor before making investment decisions.

## Contributing

Contributions and ideas are welcome. Please open an issue to discuss a change before submitting a pull request.

## License

To be decided. Add a `LICENSE` file (for example, MIT) before publishing.
