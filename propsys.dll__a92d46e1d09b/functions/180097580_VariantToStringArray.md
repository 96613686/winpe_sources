# VariantToStringArray

- ea: `0x180097580`
- end: `0x1800976f8`
- name: `VariantToStringArray`
- size: `376`
- prototype: `HRESULT __stdcall(const VARIANT *const var, PWSTR *prgsz, ULONG crgsz, ULONG *pcElem)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008ee80`

## callees

- `0x18002d070`
- `0x1800335a0`
- `0x180065b84`
- `0x18006ed20`
- `0x180097580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009767d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009767d`
- `OLEAUT32!__imp_SysFreeString` at `0x18009764f`
- `OLEAUT32!__imp_SysFreeString` at `0x18009764f`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180097616`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180097616`

## pseudocode

```c

```
