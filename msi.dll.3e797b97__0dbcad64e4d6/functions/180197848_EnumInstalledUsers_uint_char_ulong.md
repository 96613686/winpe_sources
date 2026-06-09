# EnumInstalledUsers(uint,char *,ulong)

- ea: `0x180197848`
- end: `0x180197a66`
- name: `?EnumInstalledUsers@@YAKIPEADK@Z`
- size: `542`
- prototype: `unsigned int __fastcall(DWORD dwIndex, char *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18016f264`

## callees

- `0x18003c030`
- `0x1800408a0`
- `0x180040908`
- `0x180041c54`
- `0x1800433c0`
- `0x180197848`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegEnumKeyExA` at `0x180197998`
- `ADVAPI32!RegEnumKeyExA` at `0x180197998`
- `KERNEL32!InitializeCriticalSection` at `0x1801978a4`
- `KERNEL32!InitializeCriticalSection` at `0x1801978a4`
- `KERNEL32!GlobalFree` at `0x18019792c`
- `KERNEL32!GlobalFree` at `0x1801979b4`
- `KERNEL32!GlobalFree` at `0x1801979d4`
- `KERNEL32!GlobalFree` at `0x1801979fe`
- `KERNEL32!GlobalFree` at `0x180197a1a`
- `KERNEL32!GlobalFree` at `0x18019792c`
- `KERNEL32!GlobalFree` at `0x1801979b4`
- `KERNEL32!GlobalFree` at `0x1801979d4`
- `KERNEL32!GlobalFree` at `0x1801979fe`
- `KERNEL32!GlobalFree` at `0x180197a1a`

## string_xrefs

- `0x1801978ed`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c

```
