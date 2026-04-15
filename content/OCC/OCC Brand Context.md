---
name: brand-context
description: >
  Load complete project context for Vanessa's two active brands: OCC (Origin Coffee Crafter) and Arunera. Use this skill at the START of any new conversation involving brand work, content creation, web development, SEO, automation, or strategy for either brand. Trigger whenever the user says "載入背景", "load context", "brand context", or starts a task without explaining which brand or project it belongs to. Also trigger for any task involving Next.js, Airtable, Make, Vercel, n8n, SEO/GEO content, or investor materials — these all require project context to execute correctly.
metadata:
  version: "0.1.0"
  author: "Vanessa"
---
# OCC — Origin Coffee Crafter: Full Context

## Brand Identity

- **Type**: B2B specialty coffee roaster
- **Market**: Cambodia wholesale
- **Tone**: Cold, precise, technical authority — "the Apple of coffee"
- **Voice**: Never warm or lifestyle-focused. Always data-driven, expert, credible.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | Next.js (App Router) |
| Deployment | Vercel |
| CMS | Airtable (headless, via rewritten `lib/posts.ts`) |
| Blog automation | Make → Vercel redeploy when Airtable Status → Published |
| Navigation | Hamburger / hidden MENU style |

---

## SEO Technical Rules

Apply these rules to every OCC page and article:

- **Title tags**: Front-load primary keyword
- **H1**: Must contain primary keyword (can be visible or `.sr-only`)
- **Internal links**: Absolute URLs, minimum 3 per page
- **Images**: WebP format, explicit `width` and `height` attributes, `loading="lazy"`, `srcset` for responsive sizes
- **Meta descriptions**: 150–160 characters, include primary keyword

---

## Active Work

### 1. Article Migration
- Migrating ~30 SEO articles from Google Drive → Airtable
- Each article needs: Title, Slug, Content (Markdown), Status, Meta Description, Keywords

### 2. lib/posts.ts Rewrite
- Replacing local Markdown file reads with Airtable API calls
- Must support: fetching all published posts, fetching single post by slug
- Return format must match existing Next.js page component expectations

### 3. Make Automation Pipeline
- Trigger: Airtable record Status field changes to "Published"
- Action: POST to Vercel deploy webhook URL
- Result: Vercel rebuilds and deploys the site with new content

---

## Naming & Naming Conventions

- Brand name: **OCC** or **Origin Coffee Crafter** (never lowercase "occ")
- Never appear on Arunera web properties
- File naming: kebab-case (`specialty-coffee-cambodia.md`)
- Component naming: PascalCase (`BlogPostCard.tsx`)
- CSS class naming: BEM or Tailwind utility classes

---

## Do Not Do

- Do not mix OCC and Arunera branding
- Do not use warm/lifestyle language for OCC
- Do not use relative URLs for internal links
- Do not omit image dimensions