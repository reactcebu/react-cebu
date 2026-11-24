# React Cebu

![The React Cebu homepage: a wall of photos from past meetups behind the headline "Build the web with React, right here in Cebu."](public/images/share-card.jpg)

The 2026 version of the website for React Cebu, a free community for developers learning React together in Cebu, Philippines. React Cebu is part of JavaScript Cebu.

- **Website:** https://react.jscebu.org/
- **Community:** [React Cebu on Facebook](https://www.facebook.com/reactcebu/)

Built with Next.js (App Router), React, TypeScript and Tailwind CSS v4. Animations use GSAP (ScrollTrigger, SplitText, Draggable, Inertia) with Lenis smooth scrolling. The phone on the Events page uses three.js.

## Run it

You need Node.js 20.9 or later.

```bash
npm install
npm run dev
```

Open http://localhost:3000.

| Command | What it does |
| --- | --- |
| `npm run dev` | Starts the site locally, reloading as you edit. |
| `npm run build` | Builds the site for production. Stop the dev server first. |
| `npm run start` | Serves the production build. |
| `npm run lint` | Checks the code with ESLint. |
| `npx tsc --noEmit` | Checks the types. |

## Where things live

- `src/app/` holds the pages: home, community, events, gallery and partners, plus the not found page.
- `src/data/` holds the content: gallery photos, organizers, event recaps, and the site's links and footer. Edit these files to change what the site shows.
- `src/components/` holds the sections, grouped by page, plus shared pieces like the header, footer and motion helpers.
- `src/lib/gsap.ts` registers the GSAP plugins once; `src/components/smooth-scroll.tsx` wires Lenis to ScrollTrigger.
- `public/images/` holds the photos, all from React Cebu's own events.

## Search and AI tools

- `src/lib/page-address.ts` gives each page its canonical link and share details, including the share image.
- `src/app/sitemap.ts` and `src/app/llms.txt/route.ts` list the pages.
- `src/app/page.tsx` holds the structured data.

## Deployment

The site runs on Netlify, and pushing to `main` deploys it. `SITE_URL` in `src/data/site.ts` reads Netlify's `URL` when the site builds, so the links above follow the site's main address.

## Motion

Every animation goes through `gsap.matchMedia`, so visitors who prefer reduced motion get a still page with everything in place, and Lenis stays off for them.

## Contributing

Spotted a typo, a broken link or something that looks off? Open an issue or a pull request. Before opening a pull request, run `npm run lint` and `npx tsc --noEmit`.

Every photo on the site was taken at a React Cebu event, so please don't add stock photos.

## Credits

Photos are from React Cebu's own events. Partner and community logos belong to their owners.
