# MsiGetProductCodeA

- ea: `0x180051740`
- end: `0x180051b64`
- name: `MsiGetProductCodeA`
- size: `1060`
- prototype: `UINT __stdcall(LPCSTR szComponent, LPSTR lpBuf39)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800515f0`
- `0x18016eb30`

## callees

- `0x180015950`
- `0x18001cab0`
- `0x18001d960`
- `0x180051740`
- `0x180051b70`
- `0x180055ee4`
- `0x180055f4c`
- `0x180152704`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180051885`
- `KERNEL32!InitializeCriticalSection` at `0x1800519d2`
- `KERNEL32!InitializeCriticalSection` at `0x1800519f6`
- `KERNEL32!InitializeCriticalSection` at `0x180051a92`
- `KERNEL32!InitializeCriticalSection` at `0x180051885`
- `KERNEL32!InitializeCriticalSection` at `0x1800519d2`
- `KERNEL32!InitializeCriticalSection` at `0x1800519f6`
- `KERNEL32!InitializeCriticalSection` at `0x180051a92`
- `KERNEL32!lstrlenA` at `0x180051795`
- `KERNEL32!lstrlenA` at `0x180051795`
- `KERNEL32!GlobalFree` at `0x1800518f3`
- `KERNEL32!GlobalFree` at `0x18005191a`
- `KERNEL32!GlobalFree` at `0x180051959`
- `KERNEL32!GlobalFree` at `0x18005197f`
- `KERNEL32!GlobalFree` at `0x180051acc`
- `KERNEL32!GlobalFree` at `0x180051b05`
- `KERNEL32!GlobalFree` at `0x1800518f3`
- `KERNEL32!GlobalFree` at `0x18005191a`
- `KERNEL32!GlobalFree` at `0x180051959`
- `KERNEL32!GlobalFree` at `0x18005197f`
- `KERNEL32!GlobalFree` at `0x180051acc`
- `KERNEL32!GlobalFree` at `0x180051b05`

## pseudocode

```c

```
