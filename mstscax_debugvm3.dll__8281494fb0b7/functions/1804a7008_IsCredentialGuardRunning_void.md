# IsCredentialGuardRunning(void)

- ea: `0x1804a7008`
- end: `0x1804a7755`
- name: `?IsCredentialGuardRunning@@YAHXZ`
- size: `1869`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1804e8644`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800d1db0`
- `0x1800e9b1c`
- `0x18032c818`
- `0x1804a7008`
- `0x18068c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1804a7705`
- `OLEAUT32!__imp_SysFreeString` at `0x1804a770f`
- `OLEAUT32!__imp_SysFreeString` at `0x1804a7719`
- `OLEAUT32!__imp_SysFreeString` at `0x1804a7705`
- `OLEAUT32!__imp_SysFreeString` at `0x1804a770f`
- `OLEAUT32!__imp_SysFreeString` at `0x1804a7719`
- `OLEAUT32!__imp_VariantInit` at `0x1804a7060`
- `OLEAUT32!__imp_VariantInit` at `0x1804a7060`
- `OLEAUT32!__imp_VariantClear` at `0x1804a768d`
- `OLEAUT32!__imp_VariantClear` at `0x1804a768d`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1804a74b9`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1804a74b9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804a752b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804a752b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804a74d3`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804a74d3`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1804a7593`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1804a7593`
- `OLE32!CoCreateInstance` at `0x1804a70aa`
- `OLE32!CoCreateInstance` at `0x1804a70aa`
- `OLE32!CoUninitialize` at `0x1804a76fb`
- `OLE32!CoUninitialize` at `0x1804a76fb`
- `OLE32!CoSetProxyBlanket` at `0x1804a71f3`
- `OLE32!CoSetProxyBlanket` at `0x1804a71f3`
- `OLE32!CoInitializeEx` at `0x1804a706a`
- `OLE32!CoInitializeEx` at `0x1804a706a`

## string_xrefs

- `0x1804a7142`: `deviceGuardPath.Append failed`
- `0x1804a70eb`: `CoCreateInstance(IWbemLocator) failed`
- `0x1804a743b`: `SecurityServicesRunning`
- `0x1804a7358`: `WmiClient.Query() : IWbemServices->ExecQuery()`

## pseudocode

```c

```
