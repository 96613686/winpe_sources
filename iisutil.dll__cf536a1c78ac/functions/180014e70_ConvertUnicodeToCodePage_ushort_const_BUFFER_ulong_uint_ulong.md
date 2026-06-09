# ConvertUnicodeToCodePage(ushort const *,BUFFER *,ulong,uint,ulong)

- ea: `0x180014e70`
- end: `0x180014fb3`
- name: `?ConvertUnicodeToCodePage@@YAHPEBGPEAVBUFFER@@KIK@Z`
- size: `323`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, struct BUFFER *this, unsigned int cchWideChar, UINT CodePage, DWORD dwFlags)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180001c90`
- `0x180001ee0`
- `0x180014540`
- `0x180014990`
- `0x1800158c0`
- `0x18001db60`
- `0x18001dca0`
- `0x18001e8d0`

## callees

- `0x180002da0`
- `0x180011590`
- `0x180014e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014edf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180014ec9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180014f18`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180014f67`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180014ec9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180014f18`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180014f67`

## pseudocode

```c

```
