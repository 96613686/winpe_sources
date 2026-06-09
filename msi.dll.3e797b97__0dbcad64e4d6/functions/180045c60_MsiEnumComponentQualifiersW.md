# MsiEnumComponentQualifiersW

- ea: `0x180045c60`
- end: `0x180046531`
- name: `MsiEnumComponentQualifiersW`
- size: `2257`
- prototype: `UINT __stdcall(LPCWSTR szComponent, DWORD iIndex, LPWSTR lpQualifierBuf, LPDWORD pcchQualifierBuf, LPWSTR lpApplicationDataBuf, LPDWORD pcchApplicationDataBuf)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18018d374`

## callees

- `0x18000c4bc`
- `0x180011280`
- `0x180014160`
- `0x18003c030`
- `0x180044960`
- `0x1800459c0`
- `0x180045c60`
- `0x180046538`
- `0x180046f00`
- `0x180046f50`
- `0x180048588`
- `0x1800491f0`
- `0x18004a07c`
- `0x18004c158`
- `0x18009fdf0`
- `0x1802651de`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180045ef0`
- `ADVAPI32!RegEnumValueW` at `0x180045ef0`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18004643d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18004643d`
- `ADVAPI32!RegQueryValueExW` at `0x1800464d8`
- `ADVAPI32!RegQueryValueExW` at `0x1800464d8`
- `KERNEL32!InitializeCriticalSection` at `0x180045dea`
- `KERNEL32!InitializeCriticalSection` at `0x18004618e`
- `KERNEL32!InitializeCriticalSection` at `0x180045dea`
- `KERNEL32!InitializeCriticalSection` at `0x18004618e`
- `KERNEL32!LeaveCriticalSection` at `0x180045d79`
- `KERNEL32!LeaveCriticalSection` at `0x1800463db`
- `KERNEL32!LeaveCriticalSection` at `0x180045d79`
- `KERNEL32!LeaveCriticalSection` at `0x1800463db`
- `KERNEL32!EnterCriticalSection` at `0x180045d31`
- `KERNEL32!EnterCriticalSection` at `0x180045d31`
- `KERNEL32!lstrlenW` at `0x180045cda`
- `KERNEL32!lstrlenW` at `0x180045e0d`
- `KERNEL32!lstrlenW` at `0x180045f5d`
- `KERNEL32!lstrlenW` at `0x18004623b`
- `KERNEL32!lstrlenW` at `0x180045cda`
- `KERNEL32!lstrlenW` at `0x180045e0d`
- `KERNEL32!lstrlenW` at `0x180045f5d`
- `KERNEL32!lstrlenW` at `0x18004623b`
- `KERNEL32!GlobalFree` at `0x180045faf`
- `KERNEL32!GlobalFree` at `0x180045fdd`
- `KERNEL32!GlobalFree` at `0x180046155`
- `KERNEL32!GlobalFree` at `0x1800462df`
- `KERNEL32!GlobalFree` at `0x180046349`
- `KERNEL32!GlobalFree` at `0x180045faf`
- `KERNEL32!GlobalFree` at `0x180045fdd`
- `KERNEL32!GlobalFree` at `0x180046155`
- `KERNEL32!GlobalFree` at `0x1800462df`
- `KERNEL32!GlobalFree` at `0x180046349`

## string_xrefs

- `0x180046106`: `Components`
- `0x1800461a8`: `Components`
- `0x18004638d`: `Components`

## pseudocode

```c

```
