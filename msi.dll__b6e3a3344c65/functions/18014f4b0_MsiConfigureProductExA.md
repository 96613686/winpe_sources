# MsiConfigureProductExA

- ea: `0x18014f4b0`
- end: `0x18014f92f`
- name: `MsiConfigureProductExA`
- size: `1151`
- prototype: `UINT __stdcall(LPCSTR szProduct, int iInstallLevel, INSTALLSTATE eInstallState, LPCSTR szCommandLine)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801953c0`

## callees

- `0x18000a150`
- `0x18001ba40`
- `0x18001cab0`
- `0x18001d960`
- `0x180025688`
- `0x18004ceb0`
- `0x1800c2bf0`
- `0x18014f4b0`
- `0x1801506ac`
- `0x1801516b4`
- `0x18018ec50`
- `0x180193350`
- `0x180198a30`
- `0x1801cf984`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x18014f587`
- `KERNEL32!GetModuleFileNameA` at `0x18014f587`
- `KERNEL32!lstrlenA` at `0x18014f570`
- `KERNEL32!lstrlenA` at `0x18014f60f`
- `KERNEL32!lstrlenA` at `0x18014f570`
- `KERNEL32!lstrlenA` at `0x18014f60f`
- `KERNEL32!GlobalFree` at `0x18014f704`
- `KERNEL32!GlobalFree` at `0x18014f724`
- `KERNEL32!GlobalFree` at `0x18014f751`
- `KERNEL32!GlobalFree` at `0x18014f704`
- `KERNEL32!GlobalFree` at `0x18014f724`
- `KERNEL32!GlobalFree` at `0x18014f751`
- `KERNEL32!CompareStringA` at `0x18014f5ba`
- `KERNEL32!CompareStringA` at `0x18014f5ba`

## string_xrefs

- `0x18014f544`: `Entering MsiConfigureProductEx. Product: %s, Installlevel: %d, Installstate: %d, Commandline: %s`
- `0x18014f8d3`: `MsiConfigureProductEx is returning: %u`

## pseudocode

```c

```
