# _dispatchImpl::InvokeEx(IDispatch *,DISPATCHINFO *,bool,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x1800a48fc`
- end: `0x1800a4a75`
- name: `?InvokeEx@_dispatchImpl@@SAJPEAUIDispatch@@PEAUDISPATCHINFO@@_NJKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `377`
- prototype: `HRESULT __fastcall(IDispatch *pObj, DISPATCHINFO *fCollection, bool id, int lcid, unsigned int wFlags, unsigned __int16 pdp, tagDISPPARAMS *pvarRes, tagVARIANT *pei, tagEXCEPINFO *pObj, IServiceProvider *pdispatchinfo)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x1800ddf30`
- `0x1800ec060`
- `0x180138700`

## callees

- `0x1800a48fc`
- `0x18018c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800a493b`
- `OLEAUT32!__imp_VariantInit` at `0x1800a49a5`
- `OLEAUT32!__imp_VariantInit` at `0x1800a493b`
- `OLEAUT32!__imp_VariantInit` at `0x1800a49a5`

## pseudocode

```c

```
