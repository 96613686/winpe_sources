# MsiQueryProductStateA

- ea: `0x1801a11a0`
- end: `0x1801a14f3`
- name: `MsiQueryProductStateA`
- size: `851`
- prototype: `INSTALLSTATE __stdcall(LPCSTR szProduct)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180174d90`

## callees

- `0x180014e38`
- `0x180027634`
- `0x18003c030`
- `0x180044960`
- `0x1800459c0`
- `0x1800b6f2c`
- `0x1800b8d48`
- `0x180163570`
- `0x18016f0ac`
- `0x1801954e0`
- `0x1801a11a0`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegQueryValueExA` at `0x1801a1450`
- `ADVAPI32!RegQueryValueExA` at `0x1801a1450`
- `KERNEL32!InitializeCriticalSection` at `0x1801a1283`
- `KERNEL32!InitializeCriticalSection` at `0x1801a1406`
- `KERNEL32!InitializeCriticalSection` at `0x1801a1283`
- `KERNEL32!InitializeCriticalSection` at `0x1801a1406`
- `KERNEL32!lstrlenA` at `0x1801a1204`
- `KERNEL32!lstrlenA` at `0x1801a1204`
- `KERNEL32!GlobalFree` at `0x1801a1248`
- `KERNEL32!GlobalFree` at `0x1801a1336`
- `KERNEL32!GlobalFree` at `0x1801a13b9`
- `KERNEL32!GlobalFree` at `0x1801a14ad`
- `KERNEL32!GlobalFree` at `0x1801a1248`
- `KERNEL32!GlobalFree` at `0x1801a1336`
- `KERNEL32!GlobalFree` at `0x1801a13b9`
- `KERNEL32!GlobalFree` at `0x1801a14ad`

## string_xrefs

- `0x1801a12a8`: `WindowsInstaller`
- `0x1801a1449`: `WindowsInstaller`
- `0x1801a135d`: `NOTE: non-managed installation of product %s exists, but will be ignored`

## pseudocode

```c

```
