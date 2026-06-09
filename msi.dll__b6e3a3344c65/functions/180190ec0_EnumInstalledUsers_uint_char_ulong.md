# EnumInstalledUsers(uint,char *,ulong)

- ea: `0x180190ec0`
- end: `0x1801910b3`
- name: `?EnumInstalledUsers@@YAKIPEADK@Z`
- size: `499`
- prototype: `unsigned int __fastcall(DWORD dwIndex, char *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180169250`

## callees

- `0x180015950`
- `0x180019b60`
- `0x180019bb4`
- `0x18001ba40`
- `0x180055ee4`
- `0x180190ec0`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegEnumKeyExA` at `0x180191004`
- `ADVAPI32!RegEnumKeyExA` at `0x180191004`
- `KERNEL32!InitializeCriticalSection` at `0x180190f1c`
- `KERNEL32!InitializeCriticalSection` at `0x180190f1c`
- `KERNEL32!GlobalFree` at `0x180190f9e`
- `KERNEL32!GlobalFree` at `0x18019101a`
- `KERNEL32!GlobalFree` at `0x180191034`
- `KERNEL32!GlobalFree` at `0x180191058`
- `KERNEL32!GlobalFree` at `0x18019106e`
- `KERNEL32!GlobalFree` at `0x180190f9e`
- `KERNEL32!GlobalFree` at `0x18019101a`
- `KERNEL32!GlobalFree` at `0x180191034`
- `KERNEL32!GlobalFree` at `0x180191058`
- `KERNEL32!GlobalFree` at `0x18019106e`

## string_xrefs

- `0x180190f5f`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c

```
