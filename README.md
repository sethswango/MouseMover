# MouseMover

A Windows PowerShell utility that periodically moves the cursor within a small zone near its console window and requests that Windows keep the display/session awake. It defers when it detects human mouse movement.

Run intentionally in an interactive Windows session:

```powershell
powershell.exe -NoProfile -File .\HumanMouseMover.ps1
```

The script prompts for a duration in hours (default 0.5). Press Ctrl+C to stop early. Parameters are `ZoneWidth` (140), `ZoneHeight` (90), `ZonePadding` (50), and `HumanThresholdPx` (8).

[HumanMouseMover.ps1](HumanMouseMover.ps1) is the implementation, using embedded C# and Windows APIs. [HumanMouseMover.reference.ps1](HumanMouseMover.reference.ps1) preserves the PowerShell reference implementation. No dependency manifest, build pipeline, or automated test suite is provided. Inspect or syntax-check the scripts without running them when making documentation-only changes; execution changes real cursor/power behavior. Source edits invalidate the existing signature; [re-sign the script](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-authenticodesignature?view=powershell-7.5) and [verify its signature](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-authenticodesignature?view=powershell-7.5).
