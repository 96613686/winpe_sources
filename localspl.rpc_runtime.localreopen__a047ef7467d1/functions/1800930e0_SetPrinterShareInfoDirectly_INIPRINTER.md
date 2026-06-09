# SetPrinterShareInfoDirectly(_INIPRINTER *)

- ea: `0x1800930e0`
- end: `0x1800932c1`
- name: `?SetPrinterShareInfoDirectly@@YAHPEAU_INIPRINTER@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(struct _INIPRINTER *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180058f28`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x18003ea2c`
- `0x180047330`
- `0x1800930e0`
- `0x1800934d8`
- `0x18009c908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009322b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009322b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009325c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009325c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093286`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093286`
- `SPOOLSS!DllFreeSplStr` at `0x18009328f`
- `SPOOLSS!DllFreeSplStr` at `0x180093298`
- `SPOOLSS!DllFreeSplStr` at `0x18009328f`
- `SPOOLSS!DllFreeSplStr` at `0x180093298`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800931d8`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800931d8`
- `SPOOLSS!AllocSplStr` at `0x18009314c`
- `SPOOLSS!AllocSplStr` at `0x180093168`
- `SPOOLSS!AllocSplStr` at `0x18009314c`
- `SPOOLSS!AllocSplStr` at `0x180093168`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180093265`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180093265`
- `srvcli!NetShareSetInfo` at `0x1800931fa`
- `srvcli!NetShareSetInfo` at `0x1800931fa`

## pseudocode

```c

```
