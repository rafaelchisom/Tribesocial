# The Trib3 Social: Slide Night

A copy of Slide Roulette with its own topics, logo and colours. It uses the **same Supabase project** as before, but in its own tables (`trib3_…`), so the birthday edition keeps working with its picks untouched.

## 1. Database (2 minutes)
Supabase → **SQL Editor** → New query → paste all of `supabase-setup.sql` → **Run**.
This creates the five topics and the claiming, Surprise me, swapping and suggestion features.

## 2. Website
`index.html` already has your Supabase details. Put it in a **new GitHub repo** and create a new Render **Static Site** (same settings as before: Build Command `echo "no build"`, Publish Directory `.`).

You get a link like `trib3-slide-night.onrender.com`. Share that.
(Want it on a domain, e.g. `slides.oyaquiz.com`? Add a CNAME `slides` → your onrender address in GoDaddy and add it under Custom Domains in Render.)

## On the night
Open the link → **Showtime**: running order, spin for the next presenter, a 10-minute timer with a chime, and confetti after each talk.

## Host tools (SQL Editor)
- Clear every pick, keep the topics:
  `delete from public.trib3_claim_tokens; update public.trib3_topics set claimed_by = null, claimed_at = null;`
- Remove a topic:
  `delete from public.trib3_topics where title = 'Exact title here';`
- Edit topics any time in **Table Editor → trib3_topics**.
