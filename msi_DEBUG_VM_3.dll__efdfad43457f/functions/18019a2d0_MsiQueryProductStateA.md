# MsiQueryProductStateA

- ea: `0x18019a2d0`
- end: `0x18019a5f2`
- name: `MsiQueryProductStateA`
- size: `802`
- prototype: `INSTALLSTATE __stdcall(LPCSTR szProduct)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18016ec60`

## callees

- `0x18000a150`
- `0x180015950`
- `0x18001cab0`
- `0x18001d960`
- `0x180051d20`
- `0x180055f4c`
- `0x180064a78`
- `0x18015d800`
- `0x1801690b8`
- `0x18018ec50`
- `0x18019a2d0`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegQueryValueExA` at `0x18019a55c`
- `ADVAPI32!RegQueryValueExA` at `0x18019a55c`
- `KERNEL32!InitializeCriticalSection` at `0x18019a3a7`
- `KERNEL32!InitializeCriticalSection` at `0x18019a518`
- `KERNEL32!InitializeCriticalSection` at `0x18019a3a7`
- `KERNEL32!InitializeCriticalSection` at `0x18019a518`
- `KERNEL32!lstrlenA` at `0x18019a334`
- `KERNEL32!lstrlenA` at `0x18019a334`
- `KERNEL32!GlobalFree` at `0x18019a372`
- `KERNEL32!GlobalFree` at `0x18019a454`
- `KERNEL32!GlobalFree` at `0x18019a4d1`
- `KERNEL32!GlobalFree` at `0x18019a5b3`
- `KERNEL32!GlobalFree` at `0x18019a372`
- `KERNEL32!GlobalFree` at `0x18019a454`
- `KERNEL32!GlobalFree` at `0x18019a4d1`
- `KERNEL32!GlobalFree` at `0x18019a5b3`

## string_xrefs

- `0x18019a3c6`: `WindowsInstaller`
- `0x18019a555`: `WindowsInstaller`
- `0x18019a475`: `NOTE: non-managed installation of product %s exists, but will be ignored`

## pseudocode

```c

```
