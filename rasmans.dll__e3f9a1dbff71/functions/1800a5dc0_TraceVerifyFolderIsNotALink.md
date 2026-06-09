# TraceVerifyFolderIsNotALink

- ea: `0x1800a5dc0`
- end: `0x1800a5ec1`
- name: `TraceVerifyFolderIsNotALink`
- size: `257`
- prototype: `DWORD __fastcall(HANDLE hFile, wchar_t *String1)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x1800a5254`

## callees

- `0x1800a5dc0`
- `0x1800e7260`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800a5e8e`
- `msvcrt!_wcsnicmp` at `0x1800a5e8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5e46`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800a5e0b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800a5e0b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a5e3c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a5e3c`

## pseudocode

```c

```
