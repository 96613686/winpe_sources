# DeleteCSE_EventSourceAssoc(IWbemServices *,ushort const *)

- ea: `0x1800ac740`
- end: `0x1800acb0c`
- name: `?DeleteCSE_EventSourceAssoc@@YAJPEAUIWbemServices@@PEBG@Z`
- size: `972`
- prototype: `int(struct IWbemServices *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x1800acbd8`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18003d580`
- `0x1800535a0`
- `0x1800585e8`
- `0x18005ce04`
- `0x180075ec0`
- `0x1800ac740`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ac7e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ac7e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca0e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca18`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca2c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca37`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca6c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca76`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca8a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca95`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca0e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca18`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca2c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca37`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca6c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca76`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca8a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aca95`
- `OLEAUT32!__imp_VariantInit` at `0x1800ac8fd`
- `OLEAUT32!__imp_VariantInit` at `0x1800ac973`
- `OLEAUT32!__imp_VariantInit` at `0x1800ac8fd`
- `OLEAUT32!__imp_VariantInit` at `0x1800ac973`

## string_xrefs

- `0x1800ac843`: `__PATH`
- `0x1800acabf`: `DeleteCSE_EventSourceAssoc: invalid arguments`
- `0x1800acae4`: `DeleteCSE_EventSourceAssoc: invalid arguments`
- `0x1800ac797`: `DeleteCSE_EventSourceAssoc: invalid Guid string szCSEGuid`
- `0x1800ac7bd`: `DeleteCSE_EventSourceAssoc: invalid Guid string szCSEGuid`
- `0x1800ac804`: `SELECT * FROM RSOP_ExtensionEventSourceLink WHERE extensionStatus="RSOP_ExtensionStatus.extensionGuid=\"%s\""`

## pseudocode

```c

```
