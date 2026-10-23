# Global AI Capacity Planner (prototype)

Clickable prototype for managing capacity and demand across the AI global delivery unit (UK, US, Germany, Portugal, India ring-fenced team and global delivery pool).

**All data is fictional sample data.** Edits are saved only in the viewer's browser (localStorage). There is no backend, sign-in or shared state.

## What it shows

- **Capacity view**: monthly capacity vs demand, surplus/shortfall heatmap by role, role × grade or location, bench list and won work with open seats.
- **Demand**: engagements (opportunity, stage, probability) → resource plan lines (role, grade, location, skills, quantity, FTE, dates) → bookings of named people. Team templates, paste-from-Excel and a staffing screen with ranked candidates.
- **People**: role, grade, location, pool, skills, availability, start and end dates.
- **Reference data**: roles, grades, skills, team templates, stage probabilities, bookable utilisation.

## Data model

| Table | Key fields |
|---|---|
| People | name, role, grade, location, pool, skills, capacity (FTE), start, end |
| Engagement | account, name, opportunity ID, stage, probability override, start, end, home country |
| Resource line | engagement, role, grade, location, skills, quantity, FTE each, start, end |
| Booking | resource line, person, FTE, start, end |

Demand per month = booked FTE + unfilled seats (won at 100%, pipeline weighted by stage probability).

## Running locally

It's a single static file. Open `index.html` in a browser, or serve the folder with any static server.

## Deployment

Deployed to Netlify as a static site (`netlify.toml`, publish directory is the repo root).
