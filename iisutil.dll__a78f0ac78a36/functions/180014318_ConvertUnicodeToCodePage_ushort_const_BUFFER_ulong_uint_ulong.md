# ConvertUnicodeToCodePage(ushort const *,BUFFER *,ulong,uint,ulong)

- ea: `0x180014318`
- end: `0x180014442`
- name: `?ConvertUnicodeToCodePage@@YAHPEBGPEAVBUFFER@@KIK@Z`
- size: `298`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, struct BUFFER *this, int cchWideChar, UINT CodePage, DWORD dwFlags)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180001380`
- `0x1800013f0`
- `0x180013af0`
- `0x180013f40`
- `0x180014d40`
- `0x18001cb10`
- `0x18001cc40`
- `0x18001d7b0`

## callees

- `0x180002470`
- `0x1800103f0`
- `0x180014318`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014381`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180014371`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800143b4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800143fd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180014371`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800143b4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800143fd`

## pseudocode

```c

```
