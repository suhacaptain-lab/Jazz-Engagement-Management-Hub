# Jazz Engagement Management Hub

A single-page dashboard for planning, running, and measuring engagement activities — with a month calendar, year overview, participation analytics, and a rough-planning board.

## Files
- `index.html` — the entire site. HTML, CSS, JavaScript, your logo, and the Chart.js charting library are all embedded in this one file. There are no separate `.css`, `.js`, or image files to keep track of — just upload this single file.

## What's inside
- **Month View** — full calendar grid with every activity for the month
- **Year Overview** — all 12 months at a glance, each showing which days have activities
- **📊 Engagement Analytics** — tracks overall member participation across events (not individual attendance, not satisfaction):
  - **Participation by Event** (bar chart) — participants per event
  - **Engagement Trend** (line chart) — participants over time, in chronological order, so you can see if participation is rising, falling, stable, or fluctuating
  - **Invited vs Participants** and **Avg Participation Rate by Department** — optional extras, only calculated for events where "Total Invited" is filled in
  - **Avg Participants by Event Type** — compares how different kinds of activities (Workshop, Wellness Activity, Team Building, Training, Social/Networking, or a custom type) perform
  - A detailed activity table
  - Filterable by **Event Type**, **Department**, and **Date Range** (All Time / This Month / Last 3 Months / This Year)
  - Everything updates automatically as soon as you save an activity — no manual chart updates needed
- **Planning** — a 3-column board (Idea → In Planning → Ready to Schedule) for rough brainstorming before an activity is confirmed. A "Send to Calendar" button turns a ready idea straight into a real activity.
- **All Activities sidebar** — every activity listed in date order, grouped by month (visible on the Month and Year tabs)
- Search, Upcoming/Past filters, Export to `.ics`, and Print

## Recording participation data
When creating or editing an activity, you can fill in:
- **Event Type** — Workshop, Wellness Activity, Team Building, Training, Social/Networking, or a custom type
- **Target Department** — who it's mainly for
- **Total Invited** *(optional)* — only fill this in if you have a reliable invite/eligible-member count; leave it blank otherwise
- **Total Participants** — the overall number of people who showed up (no need to track who specifically attended)

Leave Invited/Participants blank while an activity is still upcoming. The Analytics tab only counts activities with **Total Participants** filled in, and only computes a Participation Rate % for activities that also have Invited filled in — it never estimates or invents numbers.

## Deploying on GitHub Pages
1. Create a new GitHub repository (e.g. `jazz-engagement-hub`).
2. Upload just `index.html` to the repo (that's the whole site — no other files needed).
3. Go to **Settings → Pages** in the repo.
4. Under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
5. Save. GitHub will give you a live URL like `https://yourusername.github.io/jazz-engagement-hub/` within a minute or two.

## Important: about the "shared, synced" behaviour
Inside Claude, this hub saves activities and planning items to Claude's built-in shared storage, so everyone who opens the artifact sees the same live data.

**That specific sync does not carry over to GitHub Pages** — GitHub Pages just serves a static file, it has no database behind it. Once hosted there, the page automatically falls back to your **browser's local storage**, which means:
- Your data will still save and reload correctly for you.
- Each visitor's browser has its own separate copy — two different people opening the GitHub link will **not** see each other's changes.

If you want real multi-person live sync on the hosted website (not just inside Claude), you'd need to add a small backend or a service like **Firebase**, **Supabase**, or **Google Sheets as a database** behind the same UI. Happy to help wire one of those up if useful — just let me know.

In the meantime, **Export .ics** works everywhere and reliably shares the full activity list — recipients can import it straight into Outlook, Google Calendar, or Apple Calendar.

## Charts
Charts are rendered with Chart.js, which is bundled directly inside `index.html` — no internet connection or external CDN is required for the charts to work, on GitHub Pages or anywhere else.
