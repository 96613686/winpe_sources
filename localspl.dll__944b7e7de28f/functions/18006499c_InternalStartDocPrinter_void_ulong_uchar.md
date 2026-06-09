# InternalStartDocPrinter(void *,ulong,uchar *)

- ea: `0x18006499c`
- end: `0x180065077`
- name: `?InternalStartDocPrinter@@YAKPEAXKPEAE@Z`
- size: `1755`
- prototype: `unsigned int __fastcall(struct _SPOOL *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180063be4`

## callees

- `0x180006830`
- `0x180008520`
- `0x180008560`
- `0x180009630`
- `0x18000cd50`
- `0x1800298ac`
- `0x18003aad0`
- `0x18003e984`
- `0x18003ea2c`
- `0x180043148`
- `0x180043310`
- `0x180046650`
- `0x180054638`
- `0x1800601c4`
- `0x1800648d4`
- `0x180064930`
- `0x18006499c`
- `0x180065080`
- `0x18006557c`
- `0x180065ec4`
- `0x180066590`
- `0x1800723b8`
- `0x1800c5f9c`
- `0x1800ccd64`
- `0x1800da7ec`
- `0x1800dd5d0`
- `0x1800dd68c`
- `0x1800e3894`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064a0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064a25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064a0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064aa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064aa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fe0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064d36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065045`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064d36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065045`
- `SPOOLSS!DllFreeSplStr` at `0x180064fbc`
- `SPOOLSS!DllFreeSplStr` at `0x180064fbc`
- `SPOOLSS!RevertToPrinterSelf` at `0x180064a40`
- `SPOOLSS!RevertToPrinterSelf` at `0x180064a40`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180064a9f`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180064a9f`

## string_xrefs

- `0x180064a1e`: `EnablePrintJobCleanupTask`
- `0x180064a89`: `EnablePrintJobCleanupTask failed:  HRESULT 0x%08X`
- `0x180064aaf`: `ImpersonatePrinterClient failed:  Error %d`
- `0x180064d02`: `DefaultSaveAsExtension`
- `0x180064dea`: `CreatePortEntry(output file: %ws) failed, LE: %d, failing`

## pseudocode

```c

```
