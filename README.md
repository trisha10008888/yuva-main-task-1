# Attendly

**Know where you stand. Know what it takes to recover.**

Attendly is an attendance planner for students of the School of Electrical and Electronics Engineering, SRM IST Tiruchirappalli. Pick your class section, enter the attendance percentage the student portal shows for each subject, and Attendly works out:

- how many classes are left in the semester, using your section's real timetable, weekends and holidays;
- exactly how many of those you must attend to stay at or above 75%;
- how many you must attend to reach or stay above 90%;
- what you need to do before a planning date you choose;
- an **Irreversible Detention** warning when a subject can no longer reach 75% before the last instructional day, even with full attendance.

It also has:

- **Attendance Health charts**: an overall ring, per-subject bars against the 75% and 90% lines, a subject health mix and a semester breakdown of classes.
- **OD & Leave Simulator**: add On-Duty, approved medical leave (both count as present) or sick/personal leave (counts as absent) and every percentage recalculates instantly.
- **Attendance Advisor chatbot**: a floating chat that answers questions like “If I take a 3-day sick leave starting tomorrow, will my Chemistry attendance drop below 75%?” using your timetable, holidays and numbers. On GitHub Pages it runs on a built-in calculator; when opened inside Claude it uses Claude to write the reply.

There is also an attendance calendar (month and week views, with classes you can mark as attended or missed), a weekly trend graph, a what-if simulator and insights calculated from your data.

## Sections included

| Year | Sections |
|---|---|
| I | ECE-A, ECE-B, EEE, ECE-DS, Biotech-B, BME (timetable on file is dated 2024–25) |
| II | BME, ECE-DS A, ECE-DS B |
| III | BME, ECE-A, ECE-B, ECE-DS |
| IV | ECE-A, ECE-B |

Timetables are transcribed from the SEEE odd-semester 2026–27 timetables. Every section's timetable can be edited in **Settings**.

## How the numbers work

- One class = one timetable period.
- Classes attended = your percentage × classes held. "Classes held" is counted from the timetable unless you enter the portal figure.
- Classes you must attend to reach a target `t` by the end: `ceil(t × (held + remaining) − attended)`.
- If that number is more than the classes remaining, the target is unreachable. For the 75% minimum, that triggers the Irreversible Detention alert.
- Default semester dates: classes began 20 July 2026, last instructional day 30 October 2026. Both can be changed in Settings, along with the holiday list.

## Run it

It's a single static file with no build step and no dependencies.

- **Locally:** open `index.html` in a browser.
- **GitHub Pages:** push this repo, then go to **Settings → Pages → Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, and save. The site appears at `https://<your-username>.github.io/<repo-name>/`.

Everything a student enters is saved in their own browser (localStorage). Nothing is sent to a server.

## Disclaimer

Attendly is an unofficial student project. It is not affiliated with or endorsed by SRM Institute of Science and Technology. Always confirm attendance figures with the official student portal and your faculty advisor.
