# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

### Development
- `pnpm dev` or `pnpm start` - Start development server with hot module replacement
- `pnpm build` - Build for production (runs TypeScript check then Vite build)
- `pnpm preview` - Preview production build locally

### Code Quality
- `pnpm lint` - Run Biome linter
- `pnpm lint:fix` - Run Biome linter with auto-fix
- `pnpm format` - Format all files (Biome for JS/TS, Prettier for SCSS)

### Package Management
- `pnpm install` - Install dependencies (uses pnpm workspace)
- Update packages: Install `npm-check-updates` globally, then run `ncu -u` followed by `pnpm install`

## Architecture

### Build System
- **Vite** with SWC plugin for fast development and optimized builds
- **TypeScript** with strict mode enabled
- Path alias `@` maps to `./src` directory

### Project Structure
```
src/
├── main.tsx          # Entry point using React 18+ createRoot API
├── App.tsx           # Root component
├── components/       # Reusable components (functional components with hooks)
├── scss/            # SCSS stylesheets with dark/light theme support
└── assets/          # Static assets (images, SVGs)
```

### State Management
- Jotai is installed for atomic state management
- Currently using React's built-in useState for local state

### Styling
- SCSS with Dart Sass compiler
- CSS custom properties for theming
- Dark mode default with `prefers-color-scheme` support
- Global styles in `src/scss/index.scss`
- Component styles follow BEM-like naming conventions

### Code Standards
- Biome for linting and formatting (80 char line width, double quotes)
- TypeScript strict mode
- Functional components only
- Import organization enabled in Biome config