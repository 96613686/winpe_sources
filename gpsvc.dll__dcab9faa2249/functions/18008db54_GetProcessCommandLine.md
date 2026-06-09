# GetProcessCommandLine

- ea: `0x18008db54`
- end: `0x18008dee2`
- name: `GetProcessCommandLine`
- size: `910`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008dee8`

## callees

- `0x1800585e8`
- `0x18006d3c8`
- `0x18006da24`
- `0x180075ec0`
- `0x18007d320`
- `0x18007dec4`
- `0x18008c414`
- `0x18008db54`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18008de1c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18008de1c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18008dba1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18008dba1`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18008dca2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18008dca2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008de55`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008de55`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008dbe3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008dbe3`
- `OLEAUT32!__imp_VariantInit` at `0x18008ddcb`
- `OLEAUT32!__imp_VariantInit` at `0x18008ddcb`
- `OLEAUT32!__imp_VariantClear` at `0x18008de2a`
- `OLEAUT32!__imp_VariantClear` at `0x18008de2a`

## string_xrefs

- `0x18008de80`: `RPC Attribution: GetProcessCommandLine - Invalid parameters`
- `0x18008dea5`: `RPC Attribution: GetProcessCommandLine - Invalid parameters`
- `0x18008dcb3`: `SELECT CommandLine FROM Win32_Process WHERE ProcessId = %lu`
- `0x18008ddeb`: `CommandLine`

## pseudocode

```c

```
