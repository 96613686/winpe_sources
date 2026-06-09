# GetCurrentUserDirectory(void)

- ea: `0x1800dfb54`
- end: `0x1800dfc70`
- name: `?GetCurrentUserDirectory@@YAPEAGXZ`
- size: `284`
- prototype: `unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800e0b00`

## callees

- `0x180046650`
- `0x180047330`
- `0x1800df3e0`
- `0x1800df488`
- `0x1800dfb54`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dfbc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dfbc1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dfba9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dfba9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800dfc28`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800dfc28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfbfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfc09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfc30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfbfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfc09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfc30`
- `SPOOLSS!AllocSplStr` at `0x1800dfbef`
- `SPOOLSS!AllocSplStr` at `0x1800dfbef`

## string_xrefs

- `0x1800dfb9c`: `shell32.dll`
- `0x1800dfb8e`: `GetCurrentUserDirectory`
- `0x1800dfc19`: `GetCurrentUserDirectory`
- `0x1800dfc40`: `GetCurrentUserDirectory`
- `0x1800dfc00`: `Unable to get the current user directory. rc: %d`
- `0x1800dfbb7`: `SHGetFolderPathW`
- `0x1800dfc39`: `Unable to load the library Shell32.dll. rc: %d`
- `0x1800dfc0f`: `Unable to get pointer to SHGetFolderPath API in Shell32.dll. rc: %d`

## pseudocode

```c

```
