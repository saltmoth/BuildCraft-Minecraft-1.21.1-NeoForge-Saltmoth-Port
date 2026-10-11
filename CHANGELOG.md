# Changelog

These notes cover player-visible changes from BuildCraft 7.99.24.7 for Minecraft 1.12.2. The documented build is **b70** for Minecraft 1.21.1 / NeoForge. Its public binary download is currently paused.

## b70 — 2026-10-11

- English mod-list description, saltmoth adaptation credit and retained original author/license notices.
- Release documentation includes the new recipes, cropped machine interfaces, technical limits and IC2 bridge instructions.
- Gameplay code, textures and data are unchanged from b69.

### Additions and changes included in b70

- **Kinetic Accumulator:** 1,000,000 MJ storage, a shared 64 MJ/t input limit and 64 MJ/t output limit, three inputs, two outputs and a closed front display. Wooden Kinesis Pipes are required for extraction.
- Compact Accumulator and Quarry interfaces show reserves, actual throughput, status and tooltips. The Accumulator has seven BatBox-style redstone modes, comparator output and quiet activity audio.
- Compatible wrench pickup preserves the Accumulator's stored MJ. Rotation and face previews follow its port layout.
- **Optional IC2 bridge:** the matching IC2 adaptation provides a tier-3 Electrokinetic Transducer, converting EU to MJ at 16 EU/MJ and up to 16 MJ/t. There is no reverse conversion. Its recipe, interface and connections are documented in the README.
- Quarry mining and drill movement account for modern below-zero depth through a configurable cost factor. Hard energy, task and movement ceilings prevent reconnection bursts from exceeding the work limits.
- Quarry arm/laser render bounds and interior visibility corrected. Finished Quarries stop requesting energy and release work-area chunk tickets while retaining their completion state.
- Kinesis transport is demand-based: pipes have no persistent MJ reserve, and sources pay only for accepted delivery. Cutting/reconnecting long networks or rotating sources rebuilds routing without reviving stored pipe energy.
- Shared source/consumer budgets and stable flow measurements for multiple Transducers, Accumulators, branches and distant consumers.
- Chained pipe animation uses a shared phase; fluid, item and Kinesis networks remain separate. Ordinary Wooden Fluid Pipes do not attach to Kinesis networks except where the original Power Adapter permits it.
- Stacked Tanks move fluid toward the lowest available tank; modern rendering shows the Tank as a block in the inventory.
- Modern item/fluid capability integration, original side rules and IC2 fuel aliases, including Light Fuel. Raw iron/gold Macerator inputs added when the matching IC2 adaptation is installed.
- Oil deposits use native terrain, biome and water-height handling, with irregular surface pools and tapered visible gushers on land and at sea.
- Machines and networks operate in ticking chunks. A working Quarry loads its own work area; it does not silently load a remote power station. Inactive chunk connections do not trigger unrelated chunk generation.
- Network geometry/routing caches and bounded world-generation lookups reduce repeated work without changing transfer limits.

## b69 — 2026-10-11

- Removed the development suffix from the displayed BuildCraft name/version. Gameplay unchanged from the preceding delivery.

## Earlier implementation deliveries — 2026-10-09 to 2026-10-11

The additions above were developed and corrected across earlier deliveries. They are rolled into b70; older development binaries are not published here. This changelog records the final player-facing result rather than the internal sequence of patch attempts.

World-generation changes affect new chunks. Rates depend on server TPS, terrain, loaded dependencies and output capacity; no universal FPS or crash-free guarantee is implied by a release.
