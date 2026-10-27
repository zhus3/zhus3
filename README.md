<h1 align="left">Isla Ashby</h1>

I’m currently working through the messy edge cases in ocean sensor data from Scottish sea lochs: delayed buoy packets, salinity spikes after rain, and the small calibration drifts that are easy to miss until a plot stops making sense.

`Python` · `pandas` · `xarray` · `sensor QC` · `buoy telemetry` · `Oban`

---

### What I’m learning from the data

Most of my experiments are less about dramatic new methods and more about making quality-control decisions explainable. A flag should tell the next analyst whether the problem was a stuck reading, an impossible range, a suspicious rate of change, or simply a storm moving through the loch.

Recent notes I keep returning to:

- **Gap handling changes the story.** Filling every missing interval makes charts look clean, but it can hide the difference between a radio dropout and a sensor that was briefly out of the water.
- **Thresholds need context.** A chlorophyll value that looks unlikely in February may be believable during a spring bloom, so seasonal rules need careful review rather than blind automation.
- **Uncertainty is useful.** I’m experimenting with lightweight QC summaries that retain suspect values instead of silently deleting them, then make the reason visible downstream.
- **Telemetry is physical.** Weak signal, biofouling, boat wakes, heavy rain and low battery all leave fingerprints in the record.

---

### Away from the screen

On Saturdays I paddle out when the forecast is honest, usually close enough to shore that I can watch the water change colour over kelp and sand. I carry a small underwater camera, though some of the best photographs are still just the ones I remember: light through kelp fronds, a guillemot passing under the boat, or rain settling over a quiet loch.

The blog is deliberately small. I write about tides, loch geography, what a sensor saw, and what the shore looked like that week. 🌊📷

---

### Two questions I keep circling

1. **How can QC flags stay both machine-readable and interpretable?** Operational pipelines need consistent codes, but field teams and researchers also need enough context to judge whether a flagged interval reflects instrument behaviour or real environmental change.
2. **What is the right level of automation for coastal sensor networks?** Fully automated tests catch obvious faults quickly, yet over-tuned rules can remove the unusual events that matter. I’m looking for a workflow where automation triages routine checks and humans investigate the interesting edges.

These questions matter because the data often feeds several audiences: engineers maintaining equipment, scientists studying change, and local readers trying to understand the sea lochs nearby.

---

### How I work best

I prefer short scripts with obvious inputs, plain-language comments around non-obvious decisions, and tests built from real faults rather than invented perfect data. Before changing a QC rule, I like to plot the raw series, the transformed series and the affected time window on a map or station timeline.

For collaboration, I work best when notes are attached to examples. A shared notebook with three suspect buoy readings is usually more useful than a long abstract description. I also keep a paper field log; handwriting weather and sea state makes it harder to treat every odd number as a purely software problem.

<details>
<summary><strong>Supplementary notes and next steps</strong></summary>

Current experiments:

- Compare rate-of-change flags against local rainfall and tidal conditions before treating them as sensor faults.
- Build small reusable Python functions for sensor inventory metadata, packet arrival times and versioned QC flags.
- Improve visual QC reports so reviewers can move quickly from a daily summary to individual traces.
- Document recurring telemetry patterns from buoys in exposed and sheltered sea lochs.

Personal field kit checklist:

```text
split paddle · tow float · neoprene gloves
sealable notebook · camera housing · spare batteries
```

Next small blog idea: pair one kelp-forest photograph with a week of temperature, salinity and light measurements from the nearest sensor station.

</details>

---

*Profile handle: `@zhus3`. I’m usually working from Oban; replies may wait until after the weather window.* 🛶
