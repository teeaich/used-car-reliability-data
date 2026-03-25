# Used Car Engine Ratings Database

An open dataset of **2,111 combustion and electric engines** rated for reliability — across 29 brands and 987 vehicle models.

Built for [guteautoschlechteauto.de](https://guteautoschlechteauto.de), a free tool that helps used car buyers identify known weaknesses before purchase.

## Dataset Stats

| Metric | Count |
|--------|------:|
| Brands | 29 |
| Vehicle models | 987 |
| Engine variants | 2,111 |
| Vehicle configurations | 9,044 |
| Engine weaknesses | 11,699 |
| Vehicle weaknesses | 7,258 |
| **Total weaknesses** | **18,957** |

### Rating Distribution

| Rating | Count | Description |
|--------|------:|-------------|
| Recommended | 329 | Low risk — solid track record |
| Neutral | 1,324 | Average — some known issues |
| Avoid | 458 | High risk — significant or costly problems documented |

### Fuel Types

| Type | Engines |
|------|--------:|
| Petrol (Benzin) | 1,306 |
| Diesel | 666 |
| Electric | 106 |
| LPG | 20 |
| CNG | 12 |
| Hydrogen | 1 |

## Data Format

[`engines.csv`](engines.csv) contains one row per engine with the following columns:

| Column | Description | Example |
|--------|-------------|---------|
| `brand` | Manufacturer | BMW |
| `engine_code` | Internal engine code | N47D20 |
| `displacement` | Displacement + type | 2.0L Diesel |
| `fuel_type` | Fuel type (German) | Diesel |
| `rating` | Reliability rating | avoid |
| `weakness_count` | Number of known issues | 7 |
| `models` | Example models (max 5) | 3er F30; 1er F20 |
| `year_min` | Earliest production year | 2007 |
| `year_max` | Latest production year | 2014 |

## Rating Methodology

Ratings are calculated from documented weaknesses using a **top-3 worst issues** algorithm:

1. Each weakness has a **severity** (1–5) and **probability** (1–5)
2. Risk score = severity × probability (range 1–25)
3. The three highest-scoring weaknesses determine the rating:
   - **Avoid**: Any single issue scores ≥20, or top-3 average ≥13
   - **Recommended**: Top-3 average ≤8 and max score ≤10
   - **Neutral**: Everything else

This prevents engines with many minor issues from being unfairly penalized, while ensuring that a single catastrophic flaw (e.g., known timing chain failure) appropriately flags the engine.

## Brands Covered

Alfa Romeo, Audi, BMW, Citroën, Cupra, Dacia, Fiat, Ford, Honda, Hyundai, Kia, Lancia, Land Rover, Mazda, Mercedes-Benz, Mini, Mitsubishi, Nissan, Opel, Peugeot, Porsche, Renault, Seat, Škoda, Smart, Suzuki, Toyota, Volkswagen, Volvo

## Example

| Engine | Displacement | Rating | Models |
|--------|-------------|--------|--------|
| N47D20 | 2.0L Diesel | Avoid | BMW 3er F30, 1er F20 |
| B48B20 | 2.0L Turbo | Recommended | BMW 3er G20, 5er G30 |
| EA888-3B | 2.0L TSI | Neutral | VW Golf VII, Audi A3 8V |
| K9K-636 | 1.5L dCi | Neutral | Renault Clio IV, Dacia Duster |
| 2ZR-FXE | 1.8L Hybrid | Recommended | Toyota Auris E180 |

## Full Weakness Details

The CSV provides ratings and basic engine data. **Detailed weakness descriptions, repair costs, symptoms, and sources** are available on [guteautoschlechteauto.de](https://guteautoschlechteauto.de).

We also offer a **Chrome Extension** that overlays these ratings directly on [mobile.de](https://mobile.de) car listings — so you can see known issues while browsing.

## Use Cases

- **Car buyers**: Quick reliability check before viewing a car
- **Data journalists**: Analyze reliability trends across brands and fuel types
- **Developers**: Build tools on top of this dataset
- **Researchers**: Study automotive engineering reliability patterns

## License

**Data**: [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) — free for non-commercial use with attribution.

**Attribution**: Please link to [guteautoschlechteauto.de](https://guteautoschlechteauto.de) when using this data.

For commercial licensing, contact us via the website.

## Updates

This dataset is updated regularly as new weaknesses are documented and verified. Last export: March 2026.
