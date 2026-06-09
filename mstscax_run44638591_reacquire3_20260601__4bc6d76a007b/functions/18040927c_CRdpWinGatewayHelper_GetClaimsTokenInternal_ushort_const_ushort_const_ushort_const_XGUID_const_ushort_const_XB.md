# CRdpWinGatewayHelper::GetClaimsTokenInternal(ushort const *,ushort const *,ushort const *,_XGUID const *,ushort const *,_XBool32,RdpXInterfaceConstXChar16String * *)

- ea: `0x18040927c`
- end: `0x18040973d`
- name: `?GetClaimsTokenInternal@CRdpWinGatewayHelper@@AEAA?AW4_XResult32@@PEBG00PEBU_XGUID@@0W4_XBool32@@PEAPEAURdpXInterfaceConstXChar16String@@@Z`
- size: `1217`
- prototype: `enum _XResult32 __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _XGUID *, const unsigned __int16 *, enum _XBool32, struct RdpXInterfaceConstXChar16String **)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180409200`
- `0x180409240`

## callees

- `0x180022978`
- `0x18002a334`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x1800f1c88`
- `0x180101d30`
- `0x18032c818`
- `0x180407ea4`
- `0x18040927c`
- `0x1804098d8`
- `0x180688fc0`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1804094f5`
- `USER32!GetSystemMetrics` at `0x180409500`
- `USER32!GetSystemMetrics` at `0x1804094f5`
- `USER32!GetSystemMetrics` at `0x180409500`
- `OLEAUT32!__imp_SysFreeString` at `0x1804095a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1804096bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1804096cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1804096d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1804096dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1804096e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1804096f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1804095a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1804096bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1804096cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1804096d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1804096dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1804096e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1804096f5`
- `ADVAPI32!EventActivityIdControl` at `0x1804094e9`
- `ADVAPI32!EventActivityIdControl` at `0x1804096ab`
- `ADVAPI32!EventActivityIdControl` at `0x1804094e9`
- `ADVAPI32!EventActivityIdControl` at `0x1804096ab`

## string_xrefs

- `0x1804093d5`: `ppClaimsToken`
- `0x18040967f`: `Failed Auth_DllGetClaimsToken`

## pseudocode

```c

```
