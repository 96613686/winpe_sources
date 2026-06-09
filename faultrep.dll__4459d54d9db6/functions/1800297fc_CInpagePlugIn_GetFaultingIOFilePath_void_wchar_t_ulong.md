# CInpagePlugIn::GetFaultingIOFilePath(void *,wchar_t *,ulong)

- ea: `0x1800297fc`
- end: `0x180029966`
- name: `?GetFaultingIOFilePath@CInpagePlugIn@@AEAAJPEAXPEA_WK@Z`
- size: `362`
- prototype: `__int64 __fastcall(CInpagePlugIn *this, void *, wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180029c80`

## callees

- `0x180002890`
- `0x180009ed8`
- `0x180019160`
- `0x1800297fc`
- `0x18002996c`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800298d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800298d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002986d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002991d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002986d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002991d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298f7`

## string_xrefs

- `0x180029843`: `psapi.dll`

## pseudocode

```c

```
