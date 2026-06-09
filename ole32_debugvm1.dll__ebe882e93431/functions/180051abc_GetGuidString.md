# GetGuidString

- ea: `0x180051abc`
- end: `0x180051b8b`
- name: `GetGuidString`
- size: `207`
- prototype: `void __fastcall(const _GUID *rGuid, wchar_t *pstrGuid)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180051564`
- `0x180051b94`
- `0x18007317c`

## callees

- `0x180051abc`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051af5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051af5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180051b45`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180051b45`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cce27`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051b3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051b75`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051b3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051b75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051b4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051b4d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180051ad8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180051ad8`

## pseudocode

```c

```
