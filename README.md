# Ad Spend Scale Calculator

Interactive tool that models what happens to revenue and gross profit as you scale paid ad spend.

Shows the point most marketers miss: protecting ROAS usually costs you real profit, because diminishing returns mean you can often scale revenue and bank more rupees at a lower ROAS ratio.

## Features

- **Live diminishing-returns curve** — Plug in your own spend, revenue, and margin. The tool models revenue elasticity and finds the profit-maximising spend level automatically.
- **Two-slider scenario modelling** — Drag Performance and Awareness spend independently. Everything on the page updates live.
- **Gross profit + optional Net profit** — Flip the fixed costs toggle to see net profit (after agency fees, salaries, rent) alongside gross profit.
- **Profit-zone visualisation** — Main chart shows revenue curve, gross profit curve, break-even ROAS line, current dot, profit-peak dot, and your scenario dot.
- **Plain-language verdict** — Auto-generated paragraph that explains what the numbers mean, updated live.
- **5 account presets** — Mature e-com, Scaling, New brand, Lead gen, High-margin D2C. Each sets sensible defaults and elasticity.
- **Editable elasticity** — Advanced users can drag the diminishing-returns exponent with a live hint showing what it means at +10% / +20% / +100% spend.
- **Shareable links** — Every input is encoded in the URL. Copy the link, send to a client, they see your exact scenario.
- **Tangle-style draggable numbers** — Drag the bold numbers inside the narrative paragraph to change the scenario.

## How to use

1. Start with a preset chip that matches your account type, or manually enter your current spend, revenue, and margin at the top.
2. Look at the profit peak recommendation in the green bar.
3. Drag the sliders to explore alternative scenarios.
4. Copy the shareable link to send your exact scenario to a client.

## The math

- **Revenue** = `current_revenue × (new_spend / current_spend) ^ elasticity`
- **Default elasticity** = 0.76, meaning +10% spend → +7.5% revenue
- **Gross profit** = `revenue × gross_margin − total_ad_spend`
- **Net profit** (when toggled) = `gross_profit − fixed_costs`
- **Profit peak** is computed by sweeping spend and finding where gross profit is maximised
- Awareness revenue is modelled with √ growth (heavier diminishing returns, because brand-building has longer conversion windows)

Elasticity sourced from Nielsen meta-analysis of 58 CPG studies, median 0.71.

## Stack

Single static HTML file. Chart.js, no backend, no build step, no dependencies to install. Hosted on Vercel.

## Local development

No build step required. Just open `index.html` in a browser.

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## License

MIT
