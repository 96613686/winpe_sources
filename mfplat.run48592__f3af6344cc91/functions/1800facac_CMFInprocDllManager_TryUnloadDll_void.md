# CMFInprocDllManager::TryUnloadDll(void)

- ea: `0x1800facac`
- end: `0x1800fae50`
- name: `?TryUnloadDll@CMFInprocDllManager@@AEAAJXZ`
- size: `420`
- prototype: `__int64 __fastcall(CMFInprocDllManager *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180152904`
- `0x180153b6c`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800facac`
- `0x1801250c8`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800fad1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800fad1e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800fae1c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800fae1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800facc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800facc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fae38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fae38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fad2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fad2d`

## string_xrefs

- `0x1800facd3`: `CMFInprocDllManager::TryUnloadDll`
- `0x1800fada6`: `CMFInprocDllManager::TryUnloadDll`
- `0x1800fad17`: `DllCanUnloadNow`

## pseudocode

```c

```
