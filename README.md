# ARES_TASK_2
# Website Feedback — ARES Robotics (aresrobotics.in)

**Submitted by:** [Your Name]
**Department Applied For:** [e.g. Design / Web / Business]
**Date:** September 2026

---

## Overview

I went through the ARES Robotics website in detail — the About section, Departments, Projects & Events, Alumni, Competitions, Recruitment timeline, and FAQs. The content and design direction are genuinely strong; the terminal-style tags (`[ DEPT ]`, `[ PROJECT // ROVER_V1 ]`) give it a distinct identity that fits a robotics team well. I'm noting below one issue I think is worth prioritizing, followed by a few smaller suggestions.

---

## Main Issue: Page content isn't visible without JavaScript

When I checked how the site loads (using a basic HTML fetch, without letting the browser run any scripts), the page came back almost empty — just the title and a viewport tag, none of the actual text or sections. This tells me the site is fully rendered client-side (likely React), meaning all content only appears *after* the browser executes JavaScript.

**Why this matters:**

- **Search visibility:** Google can crawl JS-rendered pages, but less reliably and more slowly than pages with real HTML content upfront. For a society page trying to attract recruits and sponsors, ranking for searches like "ARES Robotics NSUT" matters.
- **Link previews:** When the site link is shared on WhatsApp, Instagram bio, or LinkedIn — which is realistically how most people will find it during outreach — there's no title, description, or preview image to show, since none of that exists in the raw HTML. It just shows up as a bare link.

**Suggested fix:**

- If the site is built with Vite + React, moving to a framework with pre-rendering support (Next.js with static generation) would resolve this properly.
- As a lighter-weight fix, adding Open Graph tags (`og:title`, `og:description`, `og:image`) and a proper `<meta name="description">` in the HTML head would fix the link-preview problem even without a full rewrite.

---

## Other Suggestions (smaller, good-to-have)

**1. Section links / deep-linking**
The site looks like one long scrolling page (About → Departments → Projects → Alumni → Competitions → Recruitment → FAQ). It would help if each section had its own URL (like `/#projects`), so a link to a specific section — say, Competitions — can be shared directly instead of always landing at the top.

**2. Recruitment results**
Right now, recruitment results are linked out to a separate spreadsheet. It might feel more polished to have a small searchable list built into the page itself (just a simple name/roll number search), so applicants don't have to leave the site.

**3. Image loading**
There are CAD previews and group photos throughout the page. Compressing these to WebP format and lazy-loading anything below the fold would help load times, especially for people checking the site on mobile data during outreach events.

**4. Basic analytics**
If not already in place, adding simple analytics (like Plausible or GA4) would help the Business team understand how many visitors reach the Recruitment section versus how many actually apply — useful for planning future outreach.

**5. Structured data for competitions**
Down the line, adding basic schema markup (Event schema) for competitions like NXP Cup or IROC could help those pages surface better when people search for those event names directly.

---

## Closing Note

Most of this is smaller polish, but the JavaScript-rendering issue is the one I'd genuinely recommend looking into soon — it affects both search visibility and how the site appears when shared, which matters a lot for a recruitment-driven page. Happy to help implement any of these if given the chance to work with the team.
