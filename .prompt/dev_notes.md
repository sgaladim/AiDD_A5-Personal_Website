# AI Prompts Log

Log at least 3 prompts you used with Copilot, Cursor, or another AI IDE.

## Prompt 1
- Prompt:Generate index.html, about.html, resume.html, projects.html, and contact.html for a personal site. Use semantic HTML (header, nav, main, footer) and a consistent navigation bar at the top. Link a shared styles.css. Include a small hero on index.html, a profile image on about.html (/images/me.jpg, with alt text), a simple resume layout on resume.html, two project cards on projects.html, and a form placeholder on contact.html. Add mobile-friendly meta tags and the same footer on every page
- AI Output (summary or pasted):Created five HTML files with a consistent <nav> containing links, <main> sections per page, a hero section on index.html, an <img> with alt on about.html, a resume list on resume.html, two project cards on projects.html, and a basic form skeleton on contact.html. All pages link styles.css and include <meta name="viewport" content="width=device-width, initial-scale=1">.
- Decision (accepted/modified/rejected) and why: I added “active link” styling via a data-page attribute on <body>, fixed missing lang="en" on <html>, and ensured every page had unique <title> text.

## Prompt 2
- Prompt:Create styles.css with a clean, modern theme using CSS variables. Include: responsive layout, a max-width container, a sticky top nav, accessible color contrast, Google Fonts import (e.g., Inter for body, Playfair Display for headings), card styles for projects, a simple grid that collapses to one column on small screens, and a @media (prefers-color-scheme: dark) section for dark mode.
- AI Output:Produced CSS with :root variables, body typography, a centered .container, sticky nav, .card components, a .grid using grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)), and a dark-mode media query flipping background/text colors. Added focus outlines and hover states.
- Decision: Accepted with minor edits. Tweaked line-height, increased contrast for links, and added .sr-only class for accessible helper text. I also added active-nav styling based on body[data-page="..."].

## Prompt 3
- Prompt: On contact.html, build an accessible contact form with labels and input id/for pairs. Fields: First Name (required), Last Name (required), Email (type=email, required), Password (minlength=8, required), Confirm Password (must match). Show inline error messages (HTML + minimal JS). Prevent submission if invalid; if valid, simulate submission and redirect to thankyou.html. Add aria-live="polite" for error container.
- AI Output:Added a form with properly labeled inputs, required, type, and minlength attributes, an email pattern fallback, and a small <script> that checks password match and form validity, sets error text in an aria-live region, and window.location.href = "thankyou.html" on success.
- Decision:I replaced pattern for email with native type="email" only (to avoid rejecting valid but unusual domains), added autocomplete attributes, and trimmed input values in JS before validation

---

## Reflection
AI assistance sped up scaffolding dramatically. Generating five linked HTML pages with consistent navigation and semantic structure would normally take me 30–45 minutes; Copilot produced a coherent baseline in under a minute that I tailored to my content. For styling, AI delivered a solid styles.css with CSS variables, a responsive grid, and dark-mode support—saving me from boilerplate and letting me focus on polish (contrast, active states, spacing). The contact form was the trickiest area where AI both helped and stumbled. It correctly wired up required fields, labels, and a basic password match, but it initially mixed native validation with an overly strict email regex and didn’t include autocomplete hints. It also forgot to trim inputs and didn’t handle active-link state across pages.

To balance AI with my own coding, I treated the outputs as drafts: I ran the pages through a mobile viewport, used a contrast checker mindset, and validated forms manually. I kept AI for repetitive structure and used my judgment for accessibility, UX details, and standards compliance. This approach preserved velocity without outsourcing critical thinking.
