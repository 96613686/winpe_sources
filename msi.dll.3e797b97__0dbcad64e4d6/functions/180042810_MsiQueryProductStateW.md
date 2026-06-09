# MsiQueryProductStateW

- ea: `0x180042810`
- end: `0x180042b54`
- name: `MsiQueryProductStateW`
- size: `836`
- prototype: `INSTALLSTATE __stdcall(LPCWSTR szProduct)`
- caller_count: `13`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180005b1c`
- `0x18000879c`
- `0x180043e60`
- `0x180085994`
- `0x180087e68`
- `0x1800eb3e8`
- `0x18011ee5c`
- `0x180140058`
- `0x18016d4ec`
- `0x180191c60`
- `0x1801d7880`
- `0x1801ec978`
- `0x180258550`

## callees

- `0x18000c4bc`
- `0x180014e38`
- `0x18003c030`
- `0x1800424b4`
- `0x180042810`
- `0x180044560`
- `0x180044960`
- `0x1800459c0`
- `0x18004a07c`
- `0x1800b2658`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180042b0e`
- `ADVAPI32!RegQueryValueExW` at `0x180042b0e`
- `KERNEL32!InitializeCriticalSection` at `0x18004289c`
- `KERNEL32!InitializeCriticalSection` at `0x180042a65`
- `KERNEL32!InitializeCriticalSection` at `0x18004289c`
- `KERNEL32!InitializeCriticalSection` at `0x180042a65`
- `KERNEL32!lstrlenW` at `0x180042867`
- `KERNEL32!lstrlenW` at `0x180042867`
- `KERNEL32!GlobalFree` at `0x180042901`
- `KERNEL32!GlobalFree` at `0x180042a1b`
- `KERNEL32!GlobalFree` at `0x180042ac2`
- `KERNEL32!GlobalFree` at `0x180042901`
- `KERNEL32!GlobalFree` at `0x180042a1b`
- `KERNEL32!GlobalFree` at `0x180042ac2`

## string_xrefs

- `0x1800428c1`: `WindowsInstaller`
- `0x180042b07`: `WindowsInstaller`
- `0x18004299e`: `NOTE: non-managed installation of product %s exists, but will be ignored`

## pseudocode

```c

```
