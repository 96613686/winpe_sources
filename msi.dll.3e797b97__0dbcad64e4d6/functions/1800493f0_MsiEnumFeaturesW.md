# MsiEnumFeaturesW

- ea: `0x1800493f0`
- end: `0x18004970f`
- name: `MsiEnumFeaturesW`
- size: `799`
- prototype: `UINT __stdcall(LPCWSTR szProduct, DWORD iFeatureIndex, LPWSTR lpFeatureBuf, LPWSTR lpParentBuf)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18004a07c`
- `0x18011aa00`
- `0x18018d374`

## callees

- `0x180011280`
- `0x180014160`
- `0x1800399d0`
- `0x18003c030`
- `0x180044960`
- `0x1800459c0`
- `0x1800491f0`
- `0x1800493f0`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180049591`
- `ADVAPI32!RegEnumValueW` at `0x180049591`
- `ADVAPI32!RegQueryValueExW` at `0x1800496a3`
- `ADVAPI32!RegQueryValueExW` at `0x1800496a3`
- `KERNEL32!InitializeCriticalSection` at `0x180049480`
- `KERNEL32!InitializeCriticalSection` at `0x180049480`
- `KERNEL32!lstrlenW` at `0x180049435`
- `KERNEL32!lstrlenW` at `0x18004949e`
- `KERNEL32!lstrlenW` at `0x180049435`
- `KERNEL32!lstrlenW` at `0x18004949e`
- `KERNEL32!GlobalFree` at `0x18004950f`
- `KERNEL32!GlobalFree` at `0x1800495dd`
- `KERNEL32!GlobalFree` at `0x1800496d5`
- `KERNEL32!GlobalFree` at `0x1800496fe`
- `KERNEL32!GlobalFree` at `0x18004950f`
- `KERNEL32!GlobalFree` at `0x1800495dd`
- `KERNEL32!GlobalFree` at `0x1800496d5`
- `KERNEL32!GlobalFree` at `0x1800496fe`

## pseudocode

```c

```
