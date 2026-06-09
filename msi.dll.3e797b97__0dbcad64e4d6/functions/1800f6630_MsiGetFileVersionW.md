# MsiGetFileVersionW

- ea: `0x1800f6630`
- end: `0x1800f6b73`
- name: `MsiGetFileVersionW`
- size: `1347`
- prototype: `UINT __stdcall(LPCWSTR szFilePath, LPWSTR lpVersionBuf, LPDWORD pcchVersionBuf, LPWSTR lpLangBuf, LPDWORD pcchLangBuf)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1800f6410`
- `0x18018f0f0`

## callees

- `0x180044960`
- `0x1800459c0`
- `0x180063e3c`
- `0x180078080`
- `0x180095144`
- `0x1800a19e0`
- `0x1800f6630`
- `0x180121fc0`
- `0x180265240`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x1800f6883`
- `KERNEL32!lstrlenW` at `0x1800f6883`
- `KERNEL32!GlobalFree` at `0x1800f674b`
- `KERNEL32!GlobalFree` at `0x1800f676b`
- `KERNEL32!GlobalFree` at `0x1800f678b`
- `KERNEL32!GlobalFree` at `0x1800f67ab`
- `KERNEL32!GlobalFree` at `0x1800f67cb`
- `KERNEL32!GlobalFree` at `0x1800f6844`
- `KERNEL32!GlobalFree` at `0x1800f6868`
- `KERNEL32!GlobalFree` at `0x1800f68fa`
- `KERNEL32!GlobalFree` at `0x1800f6927`
- `KERNEL32!GlobalFree` at `0x1800f694f`
- `KERNEL32!GlobalFree` at `0x1800f6a0c`
- `KERNEL32!GlobalFree` at `0x1800f6a38`
- `KERNEL32!GlobalFree` at `0x1800f6a82`
- `KERNEL32!GlobalFree` at `0x1800f6a9e`
- `KERNEL32!GlobalFree` at `0x1800f6ac6`
- `KERNEL32!GlobalFree` at `0x1800f6afb`
- `KERNEL32!GlobalFree` at `0x1800f6b23`
- `KERNEL32!GlobalFree` at `0x1800f674b`
- `KERNEL32!GlobalFree` at `0x1800f676b`
- `KERNEL32!GlobalFree` at `0x1800f678b`
- `KERNEL32!GlobalFree` at `0x1800f67ab`
- `KERNEL32!GlobalFree` at `0x1800f67cb`
- `KERNEL32!GlobalFree` at `0x1800f6844`
- `KERNEL32!GlobalFree` at `0x1800f6868`
- `KERNEL32!GlobalFree` at `0x1800f68fa`
- `KERNEL32!GlobalFree` at `0x1800f6927`
- `KERNEL32!GlobalFree` at `0x1800f694f`
- `KERNEL32!GlobalFree` at `0x1800f6a0c`
- `KERNEL32!GlobalFree` at `0x1800f6a38`
- `KERNEL32!GlobalFree` at `0x1800f6a82`
- `KERNEL32!GlobalFree` at `0x1800f6a9e`
- `KERNEL32!GlobalFree` at `0x1800f6ac6`
- `KERNEL32!GlobalFree` at `0x1800f6afb`
- `KERNEL32!GlobalFree` at `0x1800f6b23`
- `KERNEL32!SetErrorMode` at `0x1800f66c9`
- `KERNEL32!SetErrorMode` at `0x1800f6710`
- `KERNEL32!SetErrorMode` at `0x1800f66c9`
- `KERNEL32!SetErrorMode` at `0x1800f6710`

## pseudocode

```c

```
