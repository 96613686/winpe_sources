# MsiQueryProductStateW

- ea: `0x18001db00`
- end: `0x18001de12`
- name: `MsiQueryProductStateW`
- size: `786`
- prototype: `INSTALLSTATE __stdcall(LPCWSTR szProduct)`
- caller_count: `13`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18001c420`
- `0x18008eb18`
- `0x180090f70`
- `0x180097d10`
- `0x18009a89c`
- `0x1800e4640`
- `0x180118aac`
- `0x18013ae34`
- `0x18016751c`
- `0x18018b590`
- `0x1801cec3c`
- `0x1801e3974`
- `0x18024e238`

## callees

- `0x18001354c`
- `0x180015950`
- `0x18001cab0`
- `0x18001d960`
- `0x18001db00`
- `0x18001f190`
- `0x180025a18`
- `0x180026a8c`
- `0x18004cf08`
- `0x180064a78`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18001ddd5`
- `ADVAPI32!RegQueryValueExW` at `0x18001ddd5`
- `KERNEL32!InitializeCriticalSection` at `0x18001db86`
- `KERNEL32!InitializeCriticalSection` at `0x18001dd3c`
- `KERNEL32!InitializeCriticalSection` at `0x18001db86`
- `KERNEL32!InitializeCriticalSection` at `0x18001dd3c`
- `KERNEL32!lstrlenW` at `0x18001db57`
- `KERNEL32!lstrlenW` at `0x18001db57`
- `KERNEL32!GlobalFree` at `0x18001dbe5`
- `KERNEL32!GlobalFree` at `0x18001dcf8`
- `KERNEL32!GlobalFree` at `0x18001dd8f`
- `KERNEL32!GlobalFree` at `0x18001dbe5`
- `KERNEL32!GlobalFree` at `0x18001dcf8`
- `KERNEL32!GlobalFree` at `0x18001dd8f`

## string_xrefs

- `0x18001dba5`: `WindowsInstaller`
- `0x18001ddce`: `WindowsInstaller`
- `0x18001dc7b`: `NOTE: non-managed installation of product %s exists, but will be ignored`

## pseudocode

```c

```
