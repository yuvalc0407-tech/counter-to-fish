# CS Fish: Counter-Strike agent + arsenal in How to Fish

## The mashup (from the design interview)
You play inside **How to Fish** (host) as a **Counter-Strike agent**: CS skin and CS body size. You earn fish money by catching and killing creatures, then spend it in a **CS-style buy menu** (key B) on **Counter-Strike weapons** with CS sounds and reload feel.

- Host (role primary): How to Fish (Steam, Windows, Unity Mono). Melty has no catalog loader for it, so the build bundles BepInEx 5.
- Companion (role companion): Counter-Strike 2. Models, textures and sounds are read from the player's own install via {game:counter-strike-2}. Nothing from CS2 is shipped. CS2 is never launched or modded.
- Solo first. Co-op later.

## First playable must have
1. CS agent skin and body size
2. CS buy menu paid with fish money
3. CS gun sounds and reload feel
4. A handful of iconic guns: AK-47, AWP, Desert Eagle, knife

Out of v1: the rest of the CS arsenal, co-op, extra agents.

## Sheets (source of truth, change the sheet before the code)
weapons.json, buy_menu.json, agent.json, audio.json, hooks.json, recipe.draft.json

## Status: nothing built, nothing verified
Every `null` is an unfilled cell and every `verified:false` is unchecked. Preflight must show zero of them before the first build.

## Biggest risk
CS2 stores content in compiled Source 2 formats inside VPK archives. Sounds and textures are probably workable. **Rigged agent models and weapon animations are the hard part**: they must be read and converted into Unity objects at runtime. If that blocks the agent skin or weapon models, explain it and get agreement before changing the design.

## Not yet done (needs Melty tools + the PC's game folders)
- search_mashups / game_info / mashup_info on Melty (check for an existing similar mashup, remix option)
- Locate both installs, confirm How to Fish's engine, assemblies and mod folders
- Fill the sheets, preflight, build, test in the running game
- Listing text, credits/license/remix choice, real screenshot, inspect_package, validate_recipe, one_click_check, publish

## Continue in Claude Code or Codex on the PC
Put this folder in the project, paste the Melty publish prompt again, and add: "Design is in cs-fish-design/. The interview is done: skip the questions and build."
