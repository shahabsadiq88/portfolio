# Portfolio Website Implementation Plan

We will build a high-end, responsive personal portfolio for Shahab using **React (via Vite)**, **Tailwind CSS**, **Framer Motion**, and **Lucide React**. 

## User Review Required

> [!IMPORTANT]
> - Do you prefer using **TypeScript** with React (standard for modern apps) or plain JavaScript? I will default to TypeScript unless specified.
> - We will use Vite to initialize the React application (`npm create vite@latest . -- --template react-ts`) to provide a fast and modern SPA experience.
> - Please confirm if you want me to set up a dummy 3D glowing sphere for the Hero section using just CSS, or if you prefer an abstract avatar layout.

## Proposed Changes

### Setup & Configurations
We will initialize the basic structure and dependencies.
#### [NEW] Configuration Files (package.json, tailwind.config.js, vite.config.ts)
- Initialize Vite project.
- Install `tailwindcss`, `postcss`, `autoprefixer`, `framer-motion`, and `lucide-react`.
- Configure `tailwind.config.js` with custom colors (`black-bg`, `cyan-accent`, `gold-accent`) and custom fonts (`Syne`, `DM Sans`).

#### [MODIFY] index.html & index.css
- Import Google Fonts (Syne and DM Sans).
- Add global CSS for the grain/noise texture overlay, smooth scrolling, custom cursor hiding (so our custom cursor works flawlessly), and generic glassmorphism utility classes.

---

### Core Layout Components
Setup the foundational visual wrapper and navigation.
#### [NEW] src/components/Cursor.tsx
- A custom Framer Motion cursor with a glowing trailing effect that follows the user's mouse.
#### [NEW] src/components/Navbar.tsx
- Fixed top navigation, with `backdrop-blur` that triggers upon scrolling.
- Contains the "Shahab." logo in bold Syne font, navigation links, and a mobile hamburger menu.
#### [NEW] src/App.tsx
- Setup the main page container that incorporates the Cursor, Navbar, and sequentially mounts all individual sections.

---

### Page Sections
These will compose the main content of the single page application.

#### [NEW] src/components/Hero.tsx
- **Left:** Big text reveals, "Available for work" pulse badge, typewriter effect for "CS Student · AI Enthusiast · Builder", and CTA buttons.
- **Right:** Abstract design (CSS glowing sphere).
- **Background:** Subtle particles and horizontal scrolling marquee at the bottom.

#### [NEW] src/components/About.tsx
- Split layout with animated stats ("3+ Projects" rolling up).
- Paragraph about Shahab, timeline of journey, and 3 "What I do" cards.

#### [NEW] src/components/Projects.tsx
- Featured large glassmorphism project card for "UniMarket" (dark glass, hover lift).
- Smaller grid for 3 secondary projects.

#### [NEW] src/components/Skills.tsx
- "My Arsenal" grouped into Frontend, Backend, AI/Tools, Other.
- Animated floating pills/tags instead of boring percentage bars.

#### [NEW] src/components/Contact.tsx & src/components/Footer.tsx
- Contact form using a dark glass effect.
- Left-side massive heading, right-side inputs. Note: Form submission will be mocked (UI only) as per instructions.
- Minimalistic modern footer below the contact section.

## Open Questions

> [!WARNING]
> The contact form submission is usually handled by a backend or a service like Formspree or EmailJS. Since the prompt mentioned "No external API needed", I will build it to visually work but prevent default submission (it won't actually send an email). Let me know if you want it connected to `mailto:` or another simple method.

## Verification Plan

### Manual Verification
- We will start the development server (`npm run dev`) and test the UI in the browser using the browser subagent.
- Verify that custom fonts and tailwind styles apply correctly.
- Ensure the grain overlay and custom cursor behave smoothly without tanking layout performance.
- Test responsiveness (mobile hamburger menu, stacking layouts).
- Validate scroll-triggered animations (Framer motion `whileInView`).
