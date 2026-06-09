# MsiConfigureProductExA

- ea: `0x180154d60`
- end: `0x18015520a`
- name: `MsiConfigureProductExA`
- size: `1194`
- prototype: `UINT __stdcall(LPCSTR szProduct, int iInstallLevel, INSTALLSTATE eInstallState, LPCSTR szCommandLine)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18019c040`

## callees

- `0x180014288`
- `0x180027634`
- `0x1800433c0`
- `0x180044960`
- `0x1800459c0`
- `0x18004a014`
- `0x1800d08d0`
- `0x180154d60`
- `0x180155ff4`
- `0x180157030`
- `0x1801954e0`
- `0x180199ed4`
- `0x18019f880`
- `0x1801d86cc`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x180154e3d`
- `KERNEL32!GetModuleFileNameA` at `0x180154e3d`
- `KERNEL32!lstrlenA` at `0x180154e20`
- `KERNEL32!lstrlenA` at `0x180154ed1`
- `KERNEL32!lstrlenA` at `0x180154e20`
- `KERNEL32!lstrlenA` at `0x180154ed1`
- `KERNEL32!GlobalFree` at `0x180154fcc`
- `KERNEL32!GlobalFree` at `0x180154ff2`
- `KERNEL32!GlobalFree` at `0x180155025`
- `KERNEL32!GlobalFree` at `0x180154fcc`
- `KERNEL32!GlobalFree` at `0x180154ff2`
- `KERNEL32!GlobalFree` at `0x180155025`
- `KERNEL32!CompareStringA` at `0x180154e76`
- `KERNEL32!CompareStringA` at `0x180154e76`

## string_xrefs

- `0x180154df4`: `Entering MsiConfigureProductEx. Product: %s, Installlevel: %d, Installstate: %d, Commandline: %s`
- `0x1801551ad`: `MsiConfigureProductEx is returning: %u`

## pseudocode

```c

```
