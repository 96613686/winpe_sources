# ClearDsKey(void *,ushort *)

- ea: `0x1800a183c`
- end: `0x1800a1a08`
- name: `?ClearDsKey@@YAJPEAXPEAG@Z`
- size: `460`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004075c`

## callees

- `0x1800159d8`
- `0x18003ea2c`
- `0x18008d480`
- `0x1800a183c`
- `0x1800a6054`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1901`
- `SPOOLSS!DllFreeSplMem` at `0x1800a19ad`
- `SPOOLSS!DllFreeSplMem` at `0x1800a19ad`
- `SPOOLSS!DllAllocSplMem` at `0x1800a18f3`
- `SPOOLSS!DllAllocSplMem` at `0x1800a18f3`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800a189c`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800a189c`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800a19bb`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800a19bb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a188c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a188c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a19d6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a19d6`
- `OLEAUT32!__imp_VariantInit` at `0x1800a194b`
- `OLEAUT32!__imp_VariantInit` at `0x1800a194b`

## pseudocode

```c

```
