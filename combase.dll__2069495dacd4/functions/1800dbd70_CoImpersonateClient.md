# CoImpersonateClient

- ea: `0x1800dbd70`
- end: `0x1800dc018`
- name: `CoImpersonateClient`
- size: `680`
- prototype: `HRESULT __stdcall()`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800db84c`
- `0x1801d05e4`

## callees

- `0x18000b408`
- `0x1800188a0`
- `0x18003a8bc`
- `0x18004768c`
- `0x18008db2c`
- `0x1800dbd70`
- `0x180153648`
- `0x1801999b0`
- `0x1802135dd`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbe8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbf53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbfb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbe8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbf53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbfb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dbf7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dbf7e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dbf20`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dbf20`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800dbe5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800dbe5e`

## string_xrefs

- `0x1800dbd9d`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1800dbe57`: `comsvcs.dll`
- `0x1800dbf17`: `comsvcs.dll`

## pseudocode

```c

```
