# MsiEnumComponentQualifiersW

- ea: `0x18004e3b0`
- end: `0x18004ec16`
- name: `MsiEnumComponentQualifiersW`
- size: `2150`
- prototype: `UINT __stdcall(LPCWSTR szComponent, DWORD iIndex, LPWSTR lpQualifierBuf, LPDWORD pcchQualifierBuf, LPWSTR lpApplicationDataBuf, LPDWORD pcchApplicationDataBuf)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180186c70`

## callees

- `0x180015950`
- `0x18001cab0`
- `0x18001d960`
- `0x1800227d0`
- `0x180025560`
- `0x180025a18`
- `0x18004b560`
- `0x18004cf08`
- `0x18004e3b0`
- `0x18004ec1c`
- `0x18004f75c`
- `0x18004f7a4`
- `0x18004fa38`
- `0x18004fc48`
- `0x1800a9f70`
- `0x18025ab1e`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x18004e622`
- `ADVAPI32!RegEnumValueW` at `0x18004e622`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18004eb2e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18004eb2e`
- `ADVAPI32!RegQueryValueExW` at `0x18004ebc3`
- `ADVAPI32!RegQueryValueExW` at `0x18004ebc3`
- `KERNEL32!InitializeCriticalSection` at `0x18004e528`
- `KERNEL32!InitializeCriticalSection` at `0x18004e8a1`
- `KERNEL32!InitializeCriticalSection` at `0x18004e528`
- `KERNEL32!InitializeCriticalSection` at `0x18004e8a1`
- `KERNEL32!LeaveCriticalSection` at `0x18004e4bd`
- `KERNEL32!LeaveCriticalSection` at `0x18004ead2`
- `KERNEL32!LeaveCriticalSection` at `0x18004e4bd`
- `KERNEL32!LeaveCriticalSection` at `0x18004ead2`
- `KERNEL32!EnterCriticalSection` at `0x18004e47b`
- `KERNEL32!EnterCriticalSection` at `0x18004e47b`
- `KERNEL32!lstrlenW` at `0x18004e42a`
- `KERNEL32!lstrlenW` at `0x18004e545`
- `KERNEL32!lstrlenW` at `0x18004e689`
- `KERNEL32!lstrlenW` at `0x18004e948`
- `KERNEL32!lstrlenW` at `0x18004e42a`
- `KERNEL32!lstrlenW` at `0x18004e545`
- `KERNEL32!lstrlenW` at `0x18004e689`
- `KERNEL32!lstrlenW` at `0x18004e948`
- `KERNEL32!GlobalFree` at `0x18004e6d5`
- `KERNEL32!GlobalFree` at `0x18004e6fd`
- `KERNEL32!GlobalFree` at `0x18004e86e`
- `KERNEL32!GlobalFree` at `0x18004e9e2`
- `KERNEL32!GlobalFree` at `0x18004ea46`
- `KERNEL32!GlobalFree` at `0x18004e6d5`
- `KERNEL32!GlobalFree` at `0x18004e6fd`
- `KERNEL32!GlobalFree` at `0x18004e86e`
- `KERNEL32!GlobalFree` at `0x18004e9e2`
- `KERNEL32!GlobalFree` at `0x18004ea46`

## string_xrefs

- `0x18004e81f`: `Components`
- `0x18004e8b5`: `Components`
- `0x18004ea84`: `Components`
- `0x18004e7bb`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c

```
