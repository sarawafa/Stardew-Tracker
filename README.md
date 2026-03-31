# Stardew-Tracker

A high-fidelity, interactive web application for tracking Community Center progress in Stardew Valley. Designed as a "second-screen" companion, this tool allows players to manage bundles, filter by season, and save progress locally.

# Features
Pixel-Perfect UI: Built with a custom Stardew-inspired CSS framework, featuring the "Press Start 2P" typography and a responsive panel system.

Dynamic Seasonal Filtering: One-click toggles to show only the items available in the current in-game season (Spring, Summer, Fall, Winter).

Smart Image Engine: Programmatically fetches 100+ unique game assets from the official Stardew Wiki.

Persistent Progress: Uses localStorage to ensure your checklist remains saved even after closing the browser or refreshing the page.

Master Checklist View: A "Global" mode that aggregates every single required item into one searchable, filterable master list.

# Technical Deep Dive
Overcoming CORS & Image Hosting
One of the primary challenges was pulling high-resolution, pixelated assets directly from the Stardew Valley Wiki. Direct linking often results in CORS (Cross-Origin Resource Sharing) errors or broken paths.

Solution: I engineered a getIcon() function that utilizes the weserv.nl image proxy. This allows the app to cache, resize, and serve Wiki assets reliably while maintaining the game's iconic "pixelated" rendering style.

📊 Data Architecture
The project manages a complex nested object (bundleData) containing rooms, bundles, item locations, and seasonal availability.

Logic: The app dynamically generates UI components by iterating through this data, allowing for easy updates if game patches change item requirements.

Quality Logic: Special handling was implemented for "Quality" requirements (e.g., 5x Gold Star Melons), including a custom overlay system for the gold quality star icon.

📱 Responsive Design
The UI uses CSS Grid with auto-fit and minmax properties. This ensures the tracker looks great on a 4K monitor but remains fully functional on a smartphone—ideal for players who keep their phone on their desk while playing on a PC or console.