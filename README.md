# Gentle Games

Very simple, calm brain games for people living with Alzheimer's and other forms of dementia.

Most "easy" games on the app stores are still too much: ads, points, unlocks, level menus,
unclear instructions. Someone with dementia can't play them alone. Gentle Games is built so a
person can be handed a phone or tablet and play **independently**.

## How it plays

1. Open the app. The caregiver sees the home page, **Choose a game**, with three big tiles:
   **Pictures**, **Colors** and **Fill in the blank**. The game played last time has a darker
   outline.
2. Tap a tile and hand over the phone. That game now plays on its own, turn after turn.
3. A short instruction appears at the top and is read out loud: *"Touch the apple."*
4. Two big pictures fill the screen. The player touches one.
5. Right answer: a soft chime, a green tick, a kind word (*"Well done."*), and the next turn
   starts by itself.
6. Wrong answer: nothing bad happens. The touched answer fades away, the right one glows,
   and the instruction is said again. Every turn ends in success.
7. If nothing is touched for 12 seconds, the instruction is repeated and the right answer glows.

Once a game is running there are no scores, timers, levels, menus or back buttons on screen.
There are never ads or sign-ins.

### Games

| Game | Example | Notes |
| --- | --- | --- |
| Pictures | "Touch the dog." | ~40 everyday objects and animals |
| Colors | "Touch the blue one." | Colors that look alike to older eyes are never paired |
| Fill in the blank | "Twinkle, twinkle, little ___" → **star** / shoe | Old sayings and songs. Uses long-term memory, which often lasts longest |
| Touch the circle | One circle appears; touch it | The simplest possible version; it can't be wrong. A small link under the tiles |

A game keeps going until the caregiver changes it. It never switches on its own.

## Caregiver settings

On the home page, tap **Settings** at the bottom. During a game, press and hold the faint
circle in the **top right corner for 3 seconds**. A quick tap does nothing, so the player won't
open it by accident. From there you can:

- go back to the home page to choose a different game
- show 2, 3 or 4 answers (start with 2)
- turn the spoken instructions, the praise and the chime on or off

Settings are saved on the device.

### Keeping the player inside the game

- **iPhone / iPad:** Settings › Accessibility › Guided Access. Turn it on, open the game,
  triple-click the side (or home) button and press Start. The game is then locked on screen.
- **Android:** Settings › Security › App pinning (sometimes "Pin windows"). Pin the game.

Also turn the volume up and, if you can, turn off notifications during play.

## Putting it on a phone or tablet

Gentle Games is a web app: it runs in the phone's browser but can be added to the home screen
and then looks and works like a normal app, including with no internet connection.

1. Host it somewhere (see below) and open the link on the phone.
2. **iPhone/iPad (Safari):** Share button › *Add to Home Screen*.
   **Android (Chrome):** ⋮ menu › *Add to Home screen* / *Install app*.
3. Open it from the new icon.

### Hosting it for free with GitHub Pages

In this repository on GitHub: **Settings › Pages › Build and deployment**, choose
*Deploy from a branch*, pick the branch and the `/ (root)` folder, and save. After a minute
GitHub shows the link (something like `https://<your-username>.github.io/alzgame/`).
(GitHub Pages is free for public repositories; private repositories need a paid plan.)

### Trying it on a computer

Any static file server works, for example:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Design principles

These guide every change. If a new idea breaks one, it doesn't go in.

1. **One thing on screen at a time.** One instruction, two to four answers. Nothing else.
2. **No failure.** Wrong touches fade away quietly. No buzzers, crosses, lives or game-over.
3. **No bookkeeping.** No points, stars, streaks, levels, unlocks or "next level" buttons.
   The game simply continues.
4. **Say it and show it.** Every instruction is short, written in large type and spoken.
5. **Huge targets.** Answers fill the screen. No small buttons for the player at all.
6. **Calm and adult.** Quiet colours, real-looking pictures, no cartoon mascots or confetti.
   It should feel respectful, not childish.
7. **Caregiver controls stay out of reach.** The caregiver picks the game on the home page;
   once it's running, the controls are hidden behind a 3-second press.
8. **Works offline, no accounts, no ads, no tracking.**

## Files

- `index.html` – the whole game (layout, content and logic in one file)
- `sw.js` – lets the game work offline. Bump `CACHE` when you change any file.
- `manifest.webmanifest`, `icons/` – home-screen name and icon

## Ideas for later

- **Family photos:** "Touch Sarah." using photos the caregiver adds. Probably the most
  meaningful activity of all.
- Favourite music: finish the line of a song the player knows, played as audio.
- A gentle "same or different?" matching activity.
- Other languages and region-specific sayings.
- A caregiver-only summary of how play is going (kept off the player's screen).
- Publishing to the App Store / Google Play by wrapping the same code with Capacitor.
