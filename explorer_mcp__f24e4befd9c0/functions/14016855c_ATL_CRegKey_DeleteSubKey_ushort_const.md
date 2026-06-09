# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x14016855c`
- end: `0x140168630`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140195230`
- `0x140195804`

## callees

- `0x14016855c`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1401685ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1401685ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14016859c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1401685d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14016859c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1401685d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140168581`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140168581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140168617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140168617`

## string_xrefs

- `0x1401685b3`: `advapi32.dll`
- `0x14016857a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1401685cb`: `RegDeleteKeyW`
- `0x140168592`: `RegDeleteKeyExW`

## pseudocode

```c

```
