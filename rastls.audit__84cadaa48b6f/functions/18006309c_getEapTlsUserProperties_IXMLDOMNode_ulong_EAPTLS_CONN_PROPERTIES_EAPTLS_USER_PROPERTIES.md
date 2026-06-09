# getEapTlsUserProperties(IXMLDOMNode *,ulong,_EAPTLS_CONN_PROPERTIES *,_EAPTLS_USER_PROPERTIES * *)

- ea: `0x18006309c`
- end: `0x1800633d9`
- name: `?getEapTlsUserProperties@@YAKPEAUIXMLDOMNode@@KPEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_USER_PROPERTIES@@@Z`
- size: `829`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, unsigned int, struct _EAPTLS_CONN_PROPERTIES *, struct _EAPTLS_USER_PROPERTIES **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180062614`

## callees

- `0x180005010`
- `0x180007d00`
- `0x1800104b0`
- `0x180011d48`
- `0x1800176f0`
- `0x180021e74`
- `0x180038e4c`
- `0x18006309c`
- `0x180082010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180063346`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180063346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800632a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800632a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063375`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063383`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063375`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063383`
- `OLEAUT32!__imp_SysFreeString` at `0x180063394`
- `OLEAUT32!__imp_SysFreeString` at `0x180063394`
- `OLEAUT32!__imp_SysStringLen` at `0x1800631ca`
- `OLEAUT32!__imp_SysStringLen` at `0x1800631ca`
- `OLEAUT32!__imp_VariantInit` at `0x1800630cf`
- `OLEAUT32!__imp_VariantInit` at `0x1800630cf`
- `OLEAUT32!__imp_VariantClear` at `0x1800633a5`
- `OLEAUT32!__imp_VariantClear` at `0x1800633a5`

## pseudocode

```c

```
