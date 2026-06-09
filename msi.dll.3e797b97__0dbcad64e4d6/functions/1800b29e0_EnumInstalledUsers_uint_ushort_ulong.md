# EnumInstalledUsers(uint,ushort *,ulong)

- ea: `0x1800b29e0`
- end: `0x1800b2c32`
- name: `?EnumInstalledUsers@@YAKIPEAGK@Z`
- size: `594`
- prototype: `unsigned int __fastcall(DWORD dwIndex, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b2820`

## callees

- `0x180014160`
- `0x18003c030`
- `0x1800b29e0`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x1800b2b5d`
- `ADVAPI32!RegEnumKeyExW` at `0x1800b2b5d`
- `ADVAPI32!RegCloseKey` at `0x1800b2a63`
- `ADVAPI32!RegCloseKey` at `0x1800b2a63`
- `KERNEL32!InitializeCriticalSection` at `0x1800b2a3c`
- `KERNEL32!InitializeCriticalSection` at `0x1800b2a3c`
- `KERNEL32!LeaveCriticalSection` at `0x1800b2a87`
- `KERNEL32!LeaveCriticalSection` at `0x1800b2a87`
- `KERNEL32!EnterCriticalSection` at `0x1800b2a4d`
- `KERNEL32!EnterCriticalSection` at `0x1800b2a4d`
- `KERNEL32!GlobalFree` at `0x1800b2bae`
- `KERNEL32!GlobalFree` at `0x1800b2bfd`
- `KERNEL32!GlobalFree` at `0x1800b2c0f`
- `KERNEL32!GlobalFree` at `0x1800b2c21`
- `KERNEL32!GlobalFree` at `0x1800b2bae`
- `KERNEL32!GlobalFree` at `0x1800b2bfd`
- `KERNEL32!GlobalFree` at `0x1800b2c0f`
- `KERNEL32!GlobalFree` at `0x1800b2c21`

## string_xrefs

- `0x1800b2ab4`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c

```
