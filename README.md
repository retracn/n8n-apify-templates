# n8n workflow templates for Google News alerts, Google Shopping, Flights and Hotels price drops, Google Jobs alerts, Google Trends and app reviews (Apify)

Import-ready [n8n](https://n8n.io) workflows that run AutomationNation's Apify Actors on a schedule and send the results to Slack or Google Sheets.

| Workflow | Apify Actor |
|---|---|
| [New 1-2 star App Store reviews to Slack](app-store-bad-reviews-to-slack.json) | [app-store-reviews-scraper](https://apify.com/automationnation/app-store-reviews-scraper) |
| [Daily Google Flights price alert to Slack](daily-flight-price-alert.json) | [google-flights-scraper](https://apify.com/automationnation/google-flights-scraper) |
| [Google Flights fare drops to Slack](flight-fare-drops-to-slack.json) | [google-flights-scraper](https://apify.com/automationnation/google-flights-scraper) |
| [Google News alerts to Slack](google-news-alerts-to-slack.json) | [google-news-scraper](https://apify.com/automationnation/google-news-scraper) |
| [Google Shopping price drops to Slack](google-shopping-price-drops-to-slack.json) | [google-shopping-scraper](https://apify.com/automationnation/google-shopping-scraper) |
| [Google Hotels price drops to Slack](hotel-price-drops-to-slack.json) | [google-hotels-scraper](https://apify.com/automationnation/google-hotels-scraper) |
| [New Google Jobs postings to Slack](new-google-jobs-to-slack.json) | [google-jobs-scraper](https://apify.com/automationnation/google-jobs-scraper) |
| [Weekly Google Trends report to Google Sheets](weekly-google-trends-to-sheets.json) | [google-trends-scraper](https://apify.com/automationnation/google-trends-scraper) |

## Set up

1. Create a [free Apify account](https://console.apify.com/sign-up) and copy your API token from [Settings → API & Integrations](https://console.apify.com/settings/integrations).
2. In n8n, add a **Header Auth** credential: name `Authorization`, value `Bearer YOUR_APIFY_TOKEN`.
3. Import a workflow (Workflows → Import from file), pick the credential in its HTTP Request node, and edit the search (route, keywords or app).
4. Connect Slack or Google Sheets, then activate the workflow.

Each run calls the Actor through Apify's `run-sync-get-dataset-items` endpoint and is billed per result on your Apify account (flights $0.20 per 1,000, hotels $1 per 1,000, jobs $2 per 1,000 + $0.03 per search, keyword reports $1 per 1,000, reviews $0.08 per 1,000). Apify's free plan includes monthly credit.

More: [all AutomationNation Actors and guides](https://retracn.github.io/automationnation-actors/) · [MCP server for AI agents](https://github.com/retracn/automationnation-mcp)

MIT licensed.
