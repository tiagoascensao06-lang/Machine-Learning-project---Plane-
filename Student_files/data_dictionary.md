# Data dictionary

`learn.csv`: 16,979 rows · `predict.csv`: 4,245 rows · 40 features + `row_id` + target `fatal` (learn only).

Each row is one aviation accident: one aircraft, in the USA, from 2008 to 2023. Every column holds information available one hour after the accident. Values come from real records and were slightly altered for this project. Missing values are empty cells.

## Columns

| Column | Description | Unit |
|---|---|---|
| `row_id` | Row identifier | - |
| `ev_year` | Year of the accident | year |
| `ev_month` | Month of the accident | 1-12 |
| `ev_country` | Country where the accident happened | - |
| `ev_dow` | Day of the week of the accident | - |
| `ev_hour` | Local hour of the accident | 0-23 |
| `light_cond` | Light conditions at the time of the accident | - |
| `wx_cond_basic` | Weather conditions at the time: visual (VMC) or instrument (IMC) | - |
| `sky_cond_ceil` | Sky condition of the lowest cloud ceiling, nearest weather observation | - |
| `sky_cond_nonceil` | Sky condition of clouds that don't form a ceiling, nearest weather observation | - |
| `gust_ind` | Wind gust indicator, nearest weather observation | - |
| `sky_ceil_ht` | Height of the lowest cloud ceiling above ground, nearest weather observation | feet |
| `vis_sm` | Visibility, nearest weather observation | statute miles |
| `wx_temp` | Air temperature, nearest weather observation | degrees F |
| `wx_temp_c` | Air temperature, converted by the Guild | degrees C |
| `wx_dew_pt` | Dew point, nearest weather observation | degrees F |
| `wind_dir_deg` | Wind direction, nearest weather observation | degrees magnetic |
| `wind_vel_kts` | Wind speed, nearest weather observation | knots |
| `gust_kts` | Wind gust speed, nearest weather observation | knots |
| `altimeter` | Altimeter setting (barometric pressure; standard is 29.92), nearest weather observation | inches of mercury |
| `apt_dist` | Distance from the accident site to the nearest airport | statute miles |
| `apt_elev` | Elevation of the nearest airport | feet |
| `far_part` | Regulation the flight operated under (type of operation) | - |
| `acft_category` | Aircraft category, from the aircraft registration | - |
| `homebuilt` | Amateur-built aircraft, from the aircraft registration (Y/N) | - |
| `fixed_retractable` | Landing gear: fixed or retractable, from the aircraft type | - |
| `type_fly` | Purpose of the flight | - |
| `flt_plan_filed` | Type of flight plan filed before the flight | - |
| `second_pilot` | A second pilot was on board (Y/N) | - |
| `acft_make` | Aircraft manufacturer, from the aircraft registration | - |
| `ifr_equipped_cert` | Aircraft equipped and certified for instrument flight (1 = yes) | - |
| `num_eng` | Number of engines | count |
| `total_seats` | Total number of seats in the aircraft | count |
| `acft_year` | Year the aircraft was manufactured, from the aircraft registration | year |
| `eng_type` | Engine type | - |
| `carb_fuel_injection` | Carburettor or fuel injection | - |
| `eng_power` | Engine power: horsepower for piston and turboprop engines, pounds of thrust for jets | HP or lbs |
| `pilot_age` | Age of the pilot in command, from the pilot's FAA certificate | years |
| `pilot_sex` | Sex of the pilot in command (M/F) | - |
| `pilot_med_certf` | Medical certificate held by the pilot, from FAA records | - |
| `phase` | Phase of flight in which the accident happened, as first reported | - |
| `fatal` | **Target.** 1 = at least one fatality, 0 = none | 0/1 |

## Category codes

### `light_cond`

| Code | Meaning |
|---|---|
| `DAYL` | Day |
| `DUSK` | Dusk |
| `DAWN` | Dawn |
| `NITE` | Night |
| `NDRK` | Night, dark |
| `NBRT` | Night, bright |
| `NR` | Not reported |

### `wx_cond_basic`

| Code | Meaning |
|---|---|
| `VMC` | Visual meteorological conditions |
| `IMC` | Instrument meteorological conditions |
| `Unk` | Unknown |

### `sky_cond_ceil`

| Code | Meaning |
|---|---|
| `NONE` | No ceiling |
| `BKN` | Broken |
| `OVC` | Overcast |
| `OBSC` | Obscured |
| `VV` | Vertical visibility (indefinite) |
| `UNK` | Unknown |

### `sky_cond_nonceil`

| Code | Meaning |
|---|---|
| `CLER` | Clear |
| `FEW` | Few |
| `SCAT` | Scattered |
| `OVCT` | Thin overcast |
| `UNK` | Unknown |

### `far_part`

| Code | Meaning |
|---|---|
| `091` | Part 91: general aviation |
| `137` | Part 137: agricultural |
| `135` | Part 135: air taxi and commuter |
| `121` | Part 121: airline |
| `PUBU` | Public use |
| `133` | Part 133: rotorcraft external load |
| `129` | Part 129: foreign operator |
| `091K` | Part 91K: fractional ownership |
| `NUSN` | Non-US, non-commercial |
| `NUSC` | Non-US, commercial |
| `125` | Part 125: 20+ passengers |
| `UNK` | Unknown |

### `acft_category`

| Code | Meaning |
|---|---|
| `AIR` | Airplane |
| `HELI` | Helicopter |
| `GLI` | Glider |
| `BALL` | Balloon |
| `WSFT` | Weight-shift control |
| `GYRO` | Gyrocraft |
| `PPAR` | Powered parachute |
| `ULTR` | Ultralight |
| `PLFT` | Powered lift |
| `BLIM` | Blimp |
| `RCKT` | Rocket |
| `UNK` | Unknown |

### `fixed_retractable`

| Code | Meaning |
|---|---|
| `FIXD` | Fixed |
| `RETR` | Retractable |

### `type_fly`

| Code | Meaning |
|---|---|
| `PERS` | Personal |
| `INST` | Instructional |
| `AAPL` | Aerial application |
| `BUS` | Business |
| `POSI` | Positioning |
| `OWRK` | Other work use |
| `FLTS` | Flight test |
| `AOBV` | Aerial observation |
| `FERY` | Ferry |
| `SKYD` | Skydiving |
| `EXLD` | External load |
| `EXEC` | Executive / corporate |
| `UNK` | Unknown |
| `...` | (rarer codes: see the NTSB coding manual) |

### `flt_plan_filed`

| Code | Meaning |
|---|---|
| `NONE` | None |
| `IFR` | IFR |
| `VFR` | VFR |
| `CVFR` | Company VFR |
| `VFIF` | VFR and IFR |
| `MVFR` | Military VFR |
| `UNK` | Unknown |

### `eng_type`

| Code | Meaning |
|---|---|
| `REC` | Reciprocating (piston) |
| `TP` | Turboprop |
| `TS` | Turboshaft |
| `TF` | Turbofan |
| `TJ` | Turbojet |
| `ELEC` | Electric |
| `NONE` | No engine |
| `UNK` | Unknown |
| `...` | (rarer codes) |

### `carb_fuel_injection`

| Code | Meaning |
|---|---|
| `CARB` | Carburettor |
| `FINJ` | Fuel injected |

### `pilot_med_certf`

| Code | Meaning |
|---|---|
| `CL1` | Class 1 |
| `CL2` | Class 2 |
| `CL3` | Class 3 |
| `BASC` | BasicMed |
| `SPRT` | Sport pilot (driver's licence) |
| `NONE` | None |
| `UNK` | Unknown |

