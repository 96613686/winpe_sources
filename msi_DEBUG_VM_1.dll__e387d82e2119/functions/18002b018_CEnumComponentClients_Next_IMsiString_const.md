# CEnumComponentClients::Next(IMsiString const * &)

- ea: `0x18002b018`
- end: `0x18002b355`
- name: `?Next@CEnumComponentClients@@QEAAKAEAPEBVIMsiString@@@Z`
- size: `829`
- prototype: `unsigned int __fastcall(CEnumComponentClients *__hidden this, const struct IMsiString **)`
- caller_count: `6`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180029718`
- `0x18002bb20`
- `0x180085900`
- `0x180108854`
- `0x18012642c`
- `0x1801d0994`

## callees

- `0x180015690`
- `0x180015950`
- `0x180019b60`
- `0x180019bb4`
- `0x180022120`
- `0x18002b018`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x18002b2c6`
- `ADVAPI32!RegEnumValueW` at `0x18002b2c6`
- `ADVAPI32!RegCloseKey` at `0x18002b0d3`
- `ADVAPI32!RegCloseKey` at `0x18002b0d3`
- `KERNEL32!InitializeCriticalSection` at `0x18002b07c`
- `KERNEL32!InitializeCriticalSection` at `0x18002b07c`
- `KERNEL32!LeaveCriticalSection` at `0x18002b0ec`
- `KERNEL32!LeaveCriticalSection` at `0x18002b0ec`
- `KERNEL32!EnterCriticalSection` at `0x18002b0c3`
- `KERNEL32!EnterCriticalSection` at `0x18002b0c3`
- `KERNEL32!GlobalFree` at `0x18002b1f7`
- `KERNEL32!GlobalFree` at `0x18002b276`
- `KERNEL32!GlobalFree` at `0x18002b327`
- `KERNEL32!GlobalFree` at `0x18002b1f7`
- `KERNEL32!GlobalFree` at `0x18002b276`
- `KERNEL32!GlobalFree` at `0x18002b327`

## string_xrefs

- `0x18002b1d1`: `Components`
- `0x18002b092`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18002b190`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c

```
