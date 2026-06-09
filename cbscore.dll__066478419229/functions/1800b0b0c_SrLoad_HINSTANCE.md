# SrLoad(HINSTANCE__ * *)

- ea: `0x1800b0b0c`
- end: `0x1800b0d40`
- name: `?SrLoad@@YAJPEAPEAUHINSTANCE__@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(HINSTANCE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800f3f0c`

## callees

- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x1800b0b0c`
- `0x1800c0054`
- `0x1800eb920`
- `0x180125964`
- `0x18012b630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800b0c56`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800b0c56`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800b0b52`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800b0b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0b77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0b77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0c72`

## string_xrefs

- `0x1800b0bc9`: `Failed to load SrClient DLL: {}`
- `0x1800b0b2c`: `SrClient.dll`
- `0x1800b0b93`: `Could not load SrClient DLL from path: {}.  Continuing without system restore points.`

## pseudocode

```c

```
