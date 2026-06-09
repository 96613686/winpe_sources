# MsiInstallMissingComponentA

- ea: `0x1801554b0`
- end: `0x180155865`
- name: `MsiInstallMissingComponentA`
- size: `949`
- prototype: `UINT __stdcall(LPCSTR szProduct, LPCSTR szComponent, INSTALLSTATE eInstallState)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800079a8`
- `0x180014288`
- `0x180027634`
- `0x1800433c0`
- `0x180044960`
- `0x1800459c0`
- `0x18004a014`
- `0x18004b494`
- `0x1801554b0`
- `0x180157030`
- `0x18019a128`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18015555d`
- `KERNEL32!lstrlenA` at `0x18015557e`
- `KERNEL32!lstrlenA` at `0x18015555d`
- `KERNEL32!lstrlenA` at `0x18015557e`
- `KERNEL32!GlobalFree` at `0x1801556a4`
- `KERNEL32!GlobalFree` at `0x18015577f`
- `KERNEL32!GlobalFree` at `0x1801557aa`
- `KERNEL32!GlobalFree` at `0x1801556a4`
- `KERNEL32!GlobalFree` at `0x18015577f`
- `KERNEL32!GlobalFree` at `0x1801557aa`

## string_xrefs

- `0x1801555fd`: `COMPADDLOCAL`
- `0x1801555f4`: `COMPADDSOURCE`
- `0x1801555eb`: `COMPADDDEFAULT`
- `0x18015550b`: `Entering MsiInstallMissingComponent. Product: %s, Component: %s, Installstate: %d`
- `0x180155803`: `MsiInstallMissingComponent is returning: %u`

## pseudocode

```c

```
