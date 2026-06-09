# CRecordset::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180038070`
- end: `0x18003bd38`
- name: `?Invoke@CRecordset@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `15560`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, int, const struct _GUID *, unsigned int, unsigned __int16, struct tagDISPPARAMS *, VARIANTARG *pvarg, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18006cfa0`
- `0x18006cfb0`

## callees

- `0x180009240`
- `0x180020e50`
- `0x180020fc0`
- `0x180023090`
- `0x180023180`
- `0x180027790`
- `0x1800352c0`
- `0x180038070`
- `0x180042a04`
- `0x18006a22c`
- `0x180081760`
- `0x1800ad1a8`
- `0x1800c8f34`
- `0x1800cb55c`
- `0x1800cdaea`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x18003813c`
- `KERNEL32!TlsSetValue` at `0x18003bbdc`
- `KERNEL32!TlsSetValue` at `0x18003813c`
- `KERNEL32!TlsSetValue` at `0x18003bbdc`
- `KERNEL32!TlsGetValue` at `0x1800380f2`
- `KERNEL32!TlsGetValue` at `0x1800380f2`
- `OLEAUT32!__imp_VariantInit` at `0x180038e0e`
- `OLEAUT32!__imp_VariantInit` at `0x180038e0e`
- `OLEAUT32!__imp_VariantClear` at `0x18003bb44`
- `OLEAUT32!__imp_VariantClear` at `0x18003bb44`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18003ba48`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18003ba48`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003ba63`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003bba4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003ba63`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003bba4`

## string_xrefs

- `0x18003b675`: `<CStdComObjectRoot::PrepareInvokeArgsAndResult|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c

```
