# _dispatchImpl::InvokeEx(IDispatch *,DISPATCHINFO *,bool,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x1007541b`
- end: `0x10075530`
- name: `?InvokeEx@_dispatchImpl@@SGJPAUIDispatch@@PAUDISPATCHINFO@@_NJKGPAUtagDISPPARAMS@@PAUtagVARIANT@@PAUtagEXCEPINFO@@PAUIServiceProvider@@@Z`
- size: `277`
- prototype: `HRESULT __userpurge@<eax>(IDispatch *pObj@<ecx>, DISPATCHINFO *fCollection, bool id, int lcid, unsigned int wFlags, unsigned __int16 pdp, tagDISPPARAMS *pvarRes, tagVARIANT *pei, tagEXCEPINFO *pObj@<ecx>, IServiceProvider *pdispatchinfo)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x10088f50`
- `0x1009ef50`
- `0x100fe450`

## callees

- `0x100505bc`
- `0x10067b20`
- `0x1007541b`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x10075447`
- `OLEAUT32!__imp__VariantInit@4` at `0x10075490`
- `OLEAUT32!__imp__VariantInit@4` at `0x10075447`
- `OLEAUT32!__imp__VariantInit@4` at `0x10075490`

## pseudocode

```c

```
