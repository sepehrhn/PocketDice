# File: README.md
# PocketDice

Lightweight proximity dice rolls for **Paper/Purpur 1.21.4**.

## What it does
- `/roll [NdM]` — roll N dice with M faces.  
  Examples: `/roll` (default `1d100`), `/roll 1d6`, `/roll 2d20`, `/roll d8` (if shorthand enabled).
- Announces the result **only** to players in the same world within **radius** blocks.
- Shows player name, notation (e.g., `2d20`), individual rolls (e.g., `[7, 13]`), and total (e.g., `20`).
- Permissions: `pocketdice.roll` (true), `pocketdice.reload` (op).
- Admin: `/pocketdice reload` — reloads config & messages.

## Compatibility

### Minecraft versions
| MC Version | Status | Notes |
|---|---|---|
| 1.21 – 1.21.4 | ✅ Supported | Built against the 1.21 API (`api-version: "1.21"`). |
| < 1.21 | ❌ Not supported | Requires MC 1.21.x. |

### Server software
| Server | 1.21.x | Notes |
|---|---:|---|
| **Purpur** | ✅ | Primary target; tested. |
| **Paper** | ✅ | Supported; no Paper-only APIs used. |
| **Spigot** | ✅ | Supported via Bukkit API. |
| **Folia** | ⚠️ | Untested; should work if everything runs on main thread. |
| **Fabric / Forge / NeoForge / Quilt** | ❌ | Not applicable (those are mod loaders, not Bukkit/Paper). |

**Java:** Use Java 21 (required for MC 1.21.x servers).

## Config (`plugins/PocketDice/config.yml`)
```yml
radius: 16
default_notation: "1d100"
max_dice: 50
max_faces: 1000
message_format: "[PocketDice] {player} rolled {notation}: {results} (total {total})"
error_format: "[PocketDice] {message}"
allow_shorthand_d: true
