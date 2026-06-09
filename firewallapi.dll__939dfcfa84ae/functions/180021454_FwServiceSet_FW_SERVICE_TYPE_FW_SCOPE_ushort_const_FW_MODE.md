# FwServiceSet(FW_SERVICE_TYPE_,FW_SCOPE_,ushort const *,FW_MODE_)

- ea: `0x180021454`
- end: `0x180021622`
- name: `?FwServiceSet@@YAJW4FW_SERVICE_TYPE_@@W4FW_SCOPE_@@PEBGW4FW_MODE_@@@Z`
- size: `462`
- prototype: `int __high(enum FW_SERVICE_TYPE_, enum FW_SCOPE_, const unsigned __int16 *, enum FW_MODE_)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180021384`

## callees

- `0x180021454`
- `0x180026198`
- `0x180026c3c`
- `0x180026e1c`
- `0x1800294b0`
- `0x18003336c`
- `0x180037978`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002153f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002153f`
- `fwbase!FwNtStatusToHResult` at `0x180021558`
- `fwbase!FwNtStatusToHResult` at `0x180021558`
- `fwbase!FwReportReturnError` at `0x1800215c3`
- `fwbase!FwReportReturnError` at `0x1800215f6`
- `fwbase!FwReportReturnError` at `0x1800215c3`
- `fwbase!FwReportReturnError` at `0x1800215f6`

## string_xrefs

- `0x1800214bc`: `FwServiceSet`

## pseudocode

```c

```
