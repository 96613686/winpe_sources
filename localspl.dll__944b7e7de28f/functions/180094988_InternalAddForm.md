# InternalAddForm

- ea: `0x180094988`
- end: `0x180094d94`
- name: `InternalAddForm`
- size: `1036`
- prototype: `__int64 __fastcall(struct _INISPOOLER *, unsigned int, unsigned __int8 *, int)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180094250`
- `0x1800942e4`

## callees

- `0x1800051f0`
- `0x180005d90`
- `0x180008520`
- `0x180008560`
- `0x180008cb8`
- `0x180009630`
- `0x18000d988`
- `0x18000dd48`
- `0x18002ca24`
- `0x180035ae4`
- `0x18003ea2c`
- `0x180045010`
- `0x180046650`
- `0x180047330`
- `0x1800945a4`
- `0x1800946ac`
- `0x180094738`
- `0x180094988`
- `0x180099584`
- `0x1800ab0fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094a04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094b46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094b7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094d53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094b46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094b7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094d53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094d05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094d05`
- `SPOOLSS!DllFreeSplMem` at `0x180094cfa`
- `SPOOLSS!DllFreeSplMem` at `0x180094cfa`
- `SPOOLSS!RevertToPrinterSelf` at `0x180094ba4`
- `SPOOLSS!RevertToPrinterSelf` at `0x180094ba4`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180094d40`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180094d40`

## string_xrefs

- `0x180094b87`: `Form '%ws' already exists.`

## pseudocode

```c

```
