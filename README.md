# Paisa Patra

An offline personal investment record. One user, one phone, no server.

**Live:** https://rkvconsults-ops.github.io/paisa-patra/

## Install on iPhone

1. Open the link in **Safari** (only Safari can install to the home screen).
2. Share → **Add to Home Screen**.
3. Launch it from the icon. It runs full-screen, with no browser chrome, and works
   with no signal once the service worker has cached it.

## What it tracks

Mutual funds · shares · LIC and endowment policies · term insurance · fixed deposits ·
PPF · EPF and NPS · Sukanya Samriddhi. Plus goals, nominees (single or split by
percentage), and a claim guide for whoever has to use it.

## What it deliberately does not do

- **No live prices.** Every valuation is typed by hand. Nothing is fetched.
- **No advice.** It records and calculates. It never recommends, ranks or rates.
- **No accounts, no sync, no server.** Data lives in this phone's browser storage
  and has no route off the device except the export you perform yourself.
- **No lock screen.** Deliberate: the nominee and claim details exist so someone
  else can act in an emergency, and a PIN only you know defeats that.

## Returns

Default is invested versus current value. Add a transaction log to any holding and
it switches to **XIRR**, computed from the real dates money went in. Until then it
shows CAGR, labelled on-screen as approximate — CAGR assumes a single lump sum on
the start date, which flatters a running SIP.

## Backups matter

Data → Copy all data → paste into Mail or Notes → save the JSON into `backups/`
on the Mac. iOS can evict browser storage for an app left unused. That export is
the only durable copy. `backups/` is gitignored and never leaves the machine.

## Sources for the claim guide

- LIC claim requirements — https://licindia.in/claims-settlement-requirements
- IRDAI Bima Bharosa grievance process — https://bimabharosa.irdai.gov.in/Home/OurProcess
- Insurance Ombudsman — https://www.cioins.co.in/

Checked 2026-09-04. No claim-settlement turnaround time appears anywhere in the app,
because none could be confirmed to a primary source.

## Updating

Edit `index.html`, bump `CACHE` in `sw.js`, commit and push. Phones pick up the new
version on next launch; without the cache bump they keep serving the old one.
