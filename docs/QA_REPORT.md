# FPV Pilot Field Card Deck — QA Report

**QA date:** 2026-09-08

## Normalization completed

- All nine card faces rebuilt at **1500 × 900 px** (3 × 5 in landscape at 300 DPI).
- Common header, margins, ring-hole safe zone, panel style, typography, footer, and revision treatment applied.
- AI-generated QR imagery was discarded. All retained QR codes were regenerated from exact URLs using square modules and a 4-module quiet zone.
- QR codes were decoded from the final full-resolution PNG files with OpenCV QRCodeDetector.

## QR software-decode results

- `01_Recreational_UAS_Quick_Rules.png` → `https://www.faa.gov/uas/recreational_flyers`
- `02_Controlled_Airspace_LAANC.png` → `https://www.faa.gov/uas/getting_started/b4ufly`
- `03_FPV_Visual_Observer.png` → `No QR detected (expected for non-QR card or decoder miss)`
- `04_FTCA_Safety_Summary.png` → `https://ftca.flitetest.com/safety-guidelines/`
- `05_Preflight_Go_No_Go.png` → `https://tfr.faa.gov/tfr2/list.html`
- `06_Battery_LiPo_Quick_Reference.png` → `No QR detected (expected for non-QR card or decoder miss)`
- `07_New_Pilot_Field_Reference.png` → `No QR detected (expected for non-QR card or decoder miss)`
- `08A_Glossary_Regulatory_Airspace.png` → `No QR detected (expected for non-QR card or decoder miss)`
- `08B_Glossary_Aircraft_FPV_Battery.png` → `No QR detected (expected for non-QR card or decoder miss)`

## Factual / source review notes

1. **Recreational rule summary:** aligned to the FAA's current recreational-flyer page and active AC 91-57D.
2. **VLOS / FPV:** AC 91-57D states a co-located VO is necessary when the recreational flyer uses FPV devices that prevent scanning the surrounding airspace. The VO must be close enough for direct communication without technological assistance.
3. **Controlled airspace:** current FAA wording is Class B, C, D, and airport-associated surface Class E, with prior FAA authorization through LAANC or DroneZone.
4. **UAS Facility Maps:** retained the warning that grid values are not authorization.
5. **TRUST:** current FAA guidance requires TRUST and carriage of proof while flying.
6. **Registration / Remote ID:** revised wording to avoid the over-broad phrase “registration + Remote ID only when required.” FAA currently says drones under 250 g flown only under the recreational exception generally do not need registration; drones that are required to be registered **or are registered** must comply with Remote ID, subject to exceptions such as eligible FRIA operations.
7. **B4UFLY:** current FAA page is a provider-based service, not a single FAA mobile app. The card QR points to the FAA B4UFLY page rather than to a vendor.
8. **FTCA recognition:** FAA's current recognized-CBO list includes Flite Test Community Association.
9. **FTCA spectator spacing:** the current FTCA safety-guideline page states 25 ft lateral separation from other pilots on the flight line and 50 ft from people/spectators in the spectator area; the normalized FTCA card preserves those figures.
10. **FTCA night wording:** the FTCA page contains internally awkward wording around night lighting. The card avoids turning that into a generalized FAA rule and instead says to follow FTCA night-lighting procedures while maintaining VLOS/orientation.
11. **Terminology:** “crewed aircraft” is used in the cards for modern plain-language readability. Source pages often still use “manned aircraft.”
12. **Battery values:** the battery card remains an educational field reference. The landing and low-voltage figures are framed as conservative practical guidance, not chemistry limits or manufacturer specifications.

## Duplication matrix

| Topic | Cards | Keep repeated? | Reason |
|---|---|---|---|
| Controlled-airspace authorization | 01, 02, 05, 07, 08A | Yes, concise | Legality-critical and each appearance serves a different context |
| VLOS | 01, 03, 04, 07, 08A | Yes | Core legal + FPV operating concept |
| Yield to crewed aircraft | 01, 03, 04, 07 | Yes | Immediate collision-avoidance priority |
| TRUST | 01, 08A | Yes | Rule + glossary definition |
| Registration / Remote ID | 01, 08A | Yes | Rule + glossary explanation |
| VTX coordination | 07 only | Consolidated | Operational etiquette; no need to repeat on FTCA summary |
| Battery damage | 06, 07 | Yes, short | Safety-critical; one is battery-specific, one is incident response |
| Preflight inspection | 04, 05, 07 | Yes, compressed | CBO guidance + checklist + beginner context |
| Emergency landing | 03, 04, 05, 07 | Yes, context-specific | VO callout, FTCA rule, planning, and incident response |

## Deliberate changes from the supplied generated images

- Removed unofficial-looking logos and taglines so the deck cannot be mistaken for an official FAA or FTCA publication.
- Re-typeset all text rather than preserving generated pixels.
- Replaced every retained QR code programmatically.
- Added **VRX, FC, and ESC** to glossary Side B.
- Added a more precise Remote ID definition and registration relationship.
- Reworded B4UFLY references to reflect the current multi-provider structure.
- Consolidated VTX coordination onto the New Pilot card.
- Kept the glossary duplex relationship as 08A / 08B.
