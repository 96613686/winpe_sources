# MsiGetComponentPathW

- ea: `0x18001c420`
- end: `0x18001caa1`
- name: `MsiGetComponentPathW`
- size: `1665`
- prototype: `INSTALLSTATE __stdcall(LPCWSTR szProduct, LPCWSTR szComponent, LPWSTR lpPathBuf, LPDWORD pcchBuf)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180115a80`
- `0x18016ba40`

## callees

- `0x180014288`
- `0x180015950`
- `0x1800159d4`
- `0x18001c420`
- `0x18001cab0`
- `0x18001d960`
- `0x18001db00`
- `0x1800250d4`
- `0x18006fcf4`
- `0x1800700e0`
- `0x18008f3e8`
- `0x1800a9f70`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18001c698`
- `ADVAPI32!RegQueryValueExW` at `0x18001c698`
- `KERNEL32!InitializeCriticalSection` at `0x18001c641`
- `KERNEL32!InitializeCriticalSection` at `0x18001c641`
- `KERNEL32!lstrlenW` at `0x18001c48d`
- `KERNEL32!lstrlenW` at `0x18001c563`
- `KERNEL32!lstrlenW` at `0x18001c48d`
- `KERNEL32!lstrlenW` at `0x18001c563`
- `KERNEL32!GlobalFree` at `0x18001c71f`
- `KERNEL32!GlobalFree` at `0x18001c768`
- `KERNEL32!GlobalFree` at `0x18001c777`
- `KERNEL32!GlobalFree` at `0x18001c786`
- `KERNEL32!GlobalFree` at `0x18001c792`
- `KERNEL32!GlobalFree` at `0x18001c822`
- `KERNEL32!GlobalFree` at `0x18001c84e`
- `KERNEL32!GlobalFree` at `0x18001c887`
- `KERNEL32!GlobalFree` at `0x18001c896`
- `KERNEL32!GlobalFree` at `0x18001c8f8`
- `KERNEL32!GlobalFree` at `0x18001c96f`
- `KERNEL32!GlobalFree` at `0x18001c991`
- `KERNEL32!GlobalFree` at `0x18001c9eb`
- `KERNEL32!GlobalFree` at `0x18001ca76`
- `KERNEL32!GlobalFree` at `0x18001c71f`
- `KERNEL32!GlobalFree` at `0x18001c768`
- `KERNEL32!GlobalFree` at `0x18001c777`
- `KERNEL32!GlobalFree` at `0x18001c786`
- `KERNEL32!GlobalFree` at `0x18001c792`
- `KERNEL32!GlobalFree` at `0x18001c822`
- `KERNEL32!GlobalFree` at `0x18001c84e`
- `KERNEL32!GlobalFree` at `0x18001c887`
- `KERNEL32!GlobalFree` at `0x18001c896`
- `KERNEL32!GlobalFree` at `0x18001c8f8`
- `KERNEL32!GlobalFree` at `0x18001c96f`
- `KERNEL32!GlobalFree` at `0x18001c991`
- `KERNEL32!GlobalFree` at `0x18001c9eb`
- `KERNEL32!GlobalFree` at `0x18001ca76`

## string_xrefs

- `0x18001c527`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18001c5a6`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c

```
