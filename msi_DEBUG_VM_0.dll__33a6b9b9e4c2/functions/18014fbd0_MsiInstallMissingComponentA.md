# MsiInstallMissingComponentA

- ea: `0x18014fbd0`
- end: `0x18014ff66`
- name: `MsiInstallMissingComponentA`
- size: `918`
- prototype: `UINT __stdcall(LPCSTR szProduct, LPCSTR szComponent, INSTALLSTATE eInstallState)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a150`
- `0x18001ba40`
- `0x18001cab0`
- `0x18001d960`
- `0x180025688`
- `0x18004c5c0`
- `0x18004ceb0`
- `0x180099b50`
- `0x18014fbd0`
- `0x1801516b4`
- `0x18019358c`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18014fc7d`
- `KERNEL32!lstrlenA` at `0x18014fc98`
- `KERNEL32!lstrlenA` at `0x18014fc7d`
- `KERNEL32!lstrlenA` at `0x18014fc98`
- `KERNEL32!GlobalFree` at `0x18014fdb8`
- `KERNEL32!GlobalFree` at `0x18014fe8d`
- `KERNEL32!GlobalFree` at `0x18014feb2`
- `KERNEL32!GlobalFree` at `0x18014fdb8`
- `KERNEL32!GlobalFree` at `0x18014fe8d`
- `KERNEL32!GlobalFree` at `0x18014feb2`

## string_xrefs

- `0x18014fd11`: `COMPADDLOCAL`
- `0x18014fd08`: `COMPADDSOURCE`
- `0x18014fcff`: `COMPADDDEFAULT`
- `0x18014fc2b`: `Entering MsiInstallMissingComponent. Product: %s, Component: %s, Installstate: %d`
- `0x18014ff05`: `MsiInstallMissingComponent is returning: %u`

## pseudocode

```c

```
