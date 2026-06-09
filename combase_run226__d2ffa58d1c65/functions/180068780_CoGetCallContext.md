# CoGetCallContext

- ea: `0x180068780`
- end: `0x1800689d1`
- name: `CoGetCallContext`
- size: `593`
- prototype: `HRESULT __stdcall(const IID *const riid, void **ppInterface)`
- caller_count: `6`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180067fe0`
- `0x180068170`
- `0x180068410`
- `0x180068620`
- `0x18015dac0`
- `0x1801cee50`

## callees

- `0x1800188a0`
- `0x18004768c`
- `0x180068780`
- `0x18008db2c`
- `0x180153648`
- `0x1801999b0`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006889b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800688ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006889b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800688ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068956`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068927`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068927`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800688c8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800688c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006886b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006886b`

## string_xrefs

- `0x180068983`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180068864`: `comsvcs.dll`
- `0x1800688bf`: `comsvcs.dll`

## pseudocode

```c

```
