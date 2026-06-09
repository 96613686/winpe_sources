# CFieldsDispatch::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180021fd0`
- end: `0x180022650`
- name: `?Invoke@CFieldsDispatch@@MEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `1664`
- prototype: `__int64 __fastcall(CFieldsDispatch *__hidden this, int, const struct _GUID *, unsigned int, unsigned __int16, struct tagDISPPARAMS *, VARIANTARG *pvarg, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180020e50`
- `0x180020fc0`
- `0x180021fd0`
- `0x180023090`
- `0x180023180`
- `0x180042a04`
- `0x180053098`
- `0x180064458`
- `0x1800c8f34`
- `0x1800cb55c`
- `0x1800cdaea`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x18002205d`
- `KERNEL32!TlsSetValue` at `0x180022260`
- `KERNEL32!TlsSetValue` at `0x18002205d`
- `KERNEL32!TlsSetValue` at `0x180022260`
- `KERNEL32!TlsGetValue` at `0x180022015`
- `KERNEL32!TlsGetValue` at `0x180022015`
- `OLEAUT32!__imp_VariantInit` at `0x1800223ff`
- `OLEAUT32!__imp_VariantInit` at `0x1800223ff`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180022188`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180022188`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800221a2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002228e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800221a2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002228e`

## string_xrefs

- `0x180022502`: `<CStdComObjectRoot::PrepareInvokeArgsAndResult|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c

```
