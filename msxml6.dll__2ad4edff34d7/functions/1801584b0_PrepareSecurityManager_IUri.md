# _PrepareSecurityManager(IUri *)

- ea: `0x1801584b0`
- end: `0x1801585a8`
- name: `?_PrepareSecurityManager@@YAJPEAUIUri@@@Z`
- size: `248`
- prototype: `HRESULT __fastcall(IUri *pUri)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180158920`

## callees

- `0x1801584b0`
- `0x180185008`
- `0x1801850e0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180158525`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180158525`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1801584fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1801584fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180158549`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180158549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158504`

## string_xrefs

- `0x1801584f3`: `urlmon.dll`

## pseudocode

```c

```
