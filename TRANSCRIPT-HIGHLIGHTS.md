# Transcript Highlights

### 1. Planning the full project structure before writing any code (Session 1, early)
Before writing a single line of real code, I asked Claude to map out the entire folder structure for the app for every file, every directory, every service layer. Claude created placeholder files with comments describing what each one would do, which gave me a blueprint and prevented me from building things in the wrong order.

### 2. Setting up the Supabase client and TMDB API service files (Session 1, midway)
I asked Claude to build out the Supabase and TMDB service files so all API logic lived in one place rather than scattered across components. Claude separated it cleanly into services/supabase.js, services/tmdb.js, and services/watchlist.js, which made the rest of the app much easier to build on top of.

### 3. Moving the router and AuthProvider into App.jsx instead of main.jsx (Session 1, late)
Claude initially placed the BrowserRouter and AuthProvider in main.jsx but then caught that auth flows using useNavigate need to be inside the router context. It moved everything into App.jsx and cleaned main.jsx down to three lines. This was a good example of Claude catching its own architectural mistake before it caused bugs.

### 4. Switching from BrowserRouter to HashRouter for GitHub Pages deployment (Session 2)
After deployment the site was showing a blank screen. The issue was that BrowserRouter requires server-side routing which GitHub Pages does not support. Claude identified the problem and switched to HashRouter, which handles routing entirely on the client side and works correctly with static hosting.

### 5. Configuring vite.config.js base path and package.json homepage for GitHub Pages (Session 2)
Claude proactively added the base path configuration to vite.config.js and the homepage field to package.json before deployment. This was important because without the correct base path, all JavaScript and CSS assets would fail to load on the live site even if the HTML loaded correctly.
