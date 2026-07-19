# HUL DCF Valuation Model

A standalone discounted cash flow (DCF) valuation of Hindustan Unilever Ltd (NSE: HINDUNILVR), built from public financial data as an independent equity research / financial modeling project.

## What this is

This model builds a five-year explicit FCFF (Free Cash Flow to Firm) forecast for HUL from FY27E to FY31E, discounts it back at a WACC derived from a full CAPM build, adds a Gordon Growth terminal value, and bridges enterprise value to an intrinsic value per share. It also includes a WACC × terminal growth sensitivity grid and a relative valuation cross-check against public FMCG peers (Nestlé India, Colgate-Palmolive India, Dabur India, ITC) to sanity-check the DCF output against what the market is actually paying for comparable businesses.

The goal was to practice full end-to-end valuation modeling — sourcing and cleaning historical financials, building a defensible WACC, structuring a clean forecast, and being honest about where the model's assumptions are strong versus where they're simplifications — rather than just producing a single "fair value" number.

## Key result

The DCF implies a value of ~₹1,088/share against a current market price of ~₹2,170/share (~50% apparent downside as of 18-Jul-2026). Rather than treat that gap as a bug, the model investigates it directly: a peer-multiple cross-check (EV/EBITDA and P/E against Colgate-Palmolive India and Dabur India) implies a value of ~₹2,100–2,150/share — much closer to the market price. The takeaway isn't "the DCF is wrong" or "the market is wrong" — it's that a WACC/terminal-growth DCF is structurally conservative relative to how the market prices HUL's brand moat, pricing power, and cash-flow stability, while peer multiples capture that premium directly. Both methods are shown side by side rather than picking whichever number is more flattering.

## Structure

| Tab | Contents |
|---|---|
| Read Me | Purpose, color legend, tab guide, documented caveats, and the valuation-gap explanation above |
| Historicals | 3-year actuals (FY24–FY26), sourced from Screener.in |
| Assumptions | WACC build (CAPM), revenue growth fade, EBIT margin, tax, D&A/capex, working capital |
| FCFF Build | 5-year explicit FCFF forecast (FY27E–FY31E) |
| DCF Valuation | PV of FCFF + terminal value, bridge to equity value and value per share |
| Sensitivity | Live WACC × terminal growth grid on value per share |
| Comps Cross-Check | EV/EBITDA and P/E cross-check against FMCG peers, implied share price comparison |

## Methodology notes

- **Base year uses Operating Profit (EBIT), not net profit** — FY26 net profit and PBT are inflated by a one-off ~₹4,923 Cr Other Income spike concentrated in the Dec-2025 quarter, which also distorted the effective tax rate to 17%. Using EBIT as the FCFF base and a normalized 25.5% tax rate for all projected years keeps the forecast insulated from that anomaly.
- **Beta (~0.32)** is the figure consistent across two independent live sources (Yahoo Finance, Investing.com, both 5-year monthly), chosen after cross-checking against a wider 0.27–0.80 range across providers and excluding methodology outliers.
- **Working capital** is approximated top-down from Screener's reported Working Capital Days ratio rather than rebuilt bottom-up from receivables/inventory/payables — a deliberate simplification, documented in the Read Me tab along with the reasoning (third-party sources disagree materially on HUL's component-level days).
- All formulas are live and link across tabs — changing an assumption (e.g. WACC, terminal growth, EBIT margin) recalculates the entire model, including the sensitivity grid.

## Caveats

Every hardcoded assumption is sourced and color-coded (blue = input, black = formula, green = cross-sheet link), and every known simplification is documented explicitly in the Read Me tab rather than buried in a cell comment. This is a CV/interview-project model, not an investment recommendation — see the file for full source citations and dated data pulls.

## Files

- `HUL_DCF_Model.xlsx` — the full model

---
*Built by [Your Name] as an independent valuation project. Feedback welcome.*
