# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x14015dd00`
- end: `0x14015ddb5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140189038`
- `0x1401895c4`

## callees

- `0x14015dd00`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14015dd3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14015dd67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14015dd3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14015dd67`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14015dd52`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14015dd52`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14015dd25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14015dd25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14015dda3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14015dda3`

## string_xrefs

- `0x14015dd4b`: `advapi32.dll`
- `0x14015dd5d`: `RegDeleteKeyW`
- `0x14015dd30`: `RegDeleteKeyExW`
- `0x14015dd1e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`

## pseudocode

```c

```
