# MsiGetFileVersionW

- ea: `0x18006c790`
- end: `0x18006cc56`
- name: `MsiGetFileVersionW`
- size: `1222`
- prototype: `UINT __stdcall(LPCWSTR szFilePath, LPWSTR lpVersionBuf, LPDWORD pcchVersionBuf, LPWSTR lpLangBuf, LPDWORD pcchLangBuf)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18006c570`
- `0x180188a00`

## callees

- `0x18001cab0`
- `0x18001d960`
- `0x180056c28`
- `0x18006c790`
- `0x18006f18c`
- `0x18008a148`
- `0x1800ab728`
- `0x18011c130`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18006c9a9`
- `KERNEL32!lstrlenW` at `0x18006c9a9`
- `KERNEL32!GlobalFree` at `0x18006c89b`
- `KERNEL32!GlobalFree` at `0x18006c8b5`
- `KERNEL32!GlobalFree` at `0x18006c8cf`
- `KERNEL32!GlobalFree` at `0x18006c8e9`
- `KERNEL32!GlobalFree` at `0x18006c903`
- `KERNEL32!GlobalFree` at `0x18006c976`
- `KERNEL32!GlobalFree` at `0x18006c994`
- `KERNEL32!GlobalFree` at `0x18006ca1a`
- `KERNEL32!GlobalFree` at `0x18006ca41`
- `KERNEL32!GlobalFree` at `0x18006ca63`
- `KERNEL32!GlobalFree` at `0x18006cb1a`
- `KERNEL32!GlobalFree` at `0x18006cb40`
- `KERNEL32!GlobalFree` at `0x18006cb84`
- `KERNEL32!GlobalFree` at `0x18006cb9a`
- `KERNEL32!GlobalFree` at `0x18006cbbc`
- `KERNEL32!GlobalFree` at `0x18006cbeb`
- `KERNEL32!GlobalFree` at `0x18006cc0d`
- `KERNEL32!GlobalFree` at `0x18006c89b`
- `KERNEL32!GlobalFree` at `0x18006c8b5`
- `KERNEL32!GlobalFree` at `0x18006c8cf`
- `KERNEL32!GlobalFree` at `0x18006c8e9`
- `KERNEL32!GlobalFree` at `0x18006c903`
- `KERNEL32!GlobalFree` at `0x18006c976`
- `KERNEL32!GlobalFree` at `0x18006c994`
- `KERNEL32!GlobalFree` at `0x18006ca1a`
- `KERNEL32!GlobalFree` at `0x18006ca41`
- `KERNEL32!GlobalFree` at `0x18006ca63`
- `KERNEL32!GlobalFree` at `0x18006cb1a`
- `KERNEL32!GlobalFree` at `0x18006cb40`
- `KERNEL32!GlobalFree` at `0x18006cb84`
- `KERNEL32!GlobalFree` at `0x18006cb9a`
- `KERNEL32!GlobalFree` at `0x18006cbbc`
- `KERNEL32!GlobalFree` at `0x18006cbeb`
- `KERNEL32!GlobalFree` at `0x18006cc0d`
- `KERNEL32!SetErrorMode` at `0x18006c829`
- `KERNEL32!SetErrorMode` at `0x18006c86a`
- `KERNEL32!SetErrorMode` at `0x18006c829`
- `KERNEL32!SetErrorMode` at `0x18006c86a`

## pseudocode

```c

```
