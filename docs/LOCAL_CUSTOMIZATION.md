# Retained local build — 2026-10-25

This branch preserves the customized CellDock 0.3.1 installation used on an Apple Silicon Mac. It is based on upstream tag `0.3.1` (d77c259), rather than replacing the newer fork main branch.

- Hide generated module-number labels and omit separators around empty labels in SIM, calls, and summaries.
- Restore the standalone Sounds settings page, bundled sound selection and preview, custom audio import, and reset-to-default controls from upstream main.
- Include microphone and Contacts usage entitlements in application signing.
- Package all bundled audio resources.

`dist/CellDock-final-2026-10-25.zip` contains the exact retained installed application (Apple Silicon / arm64). SHA-256: `0ecf53ce441106c1cd746a11a9a1373d1f006acbdbc31a74a4c6708d9bc7ac40`.

The retained app uses a local ad-hoc signature and is not Apple-notarized. It allows library-signature differences within this app to load the original signed Sparkle framework. The system privacy database and system security settings are not modified. Official updates can replace these customizations. The archive contains application code and bundled resources only, without contacts, SMS, recordings, account data, or local preferences.

Validation: release compilation with Swift 6.4 on macOS; all nine bundled sound files present; `codesign --verify --deep --strict` passed. Local builds used the installed Sparkle framework to avoid a redundant dependency download; the committed Package.swift retains the portable upstream Sparkle dependency.
