# _dispatchImpl::InvokeEx(IDispatch *,DISPATCHINFO *,bool,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x1800a41e0`
- end: `0x1800a434c`
- name: `?InvokeEx@_dispatchImpl@@SAJPEAUIDispatch@@PEAUDISPATCHINFO@@_NJKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `364`
- prototype: `HRESULT __fastcall(IDispatch *pObj, DISPATCHINFO *fCollection, bool id, int lcid, unsigned int wFlags, unsigned __int16 pdp, tagDISPPARAMS *pvarRes, tagVARIANT *pei, tagEXCEPINFO *pObj, IServiceProvider *pdispatchinfo)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x1800dbfd0`
- `0x1800e9ec0`
- `0x180135920`

## callees

- `0x1800a41e0`
- `0x180188010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800a421f`
- `OLEAUT32!__imp_VariantInit` at `0x1800a4283`
- `OLEAUT32!__imp_VariantInit` at `0x1800a421f`
- `OLEAUT32!__imp_VariantInit` at `0x1800a4283`

## pseudocode

```c

```
