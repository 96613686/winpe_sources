# _dispatchImpl::InvokeEx(IDispatch *,DISPATCHINFO *,bool,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x100753eb`
- end: `0x10075500`
- name: `?InvokeEx@_dispatchImpl@@SGJPAUIDispatch@@PAUDISPATCHINFO@@_NJKGPAUtagDISPPARAMS@@PAUtagVARIANT@@PAUtagEXCEPINFO@@PAUIServiceProvider@@@Z`
- size: `277`
- prototype: `HRESULT __userpurge@<eax>(IDispatch *pObj@<ecx>, DISPATCHINFO *fCollection, bool id, int lcid, unsigned int wFlags, unsigned __int16 pdp, tagDISPPARAMS *pvarRes, tagVARIANT *pei, tagEXCEPINFO *pObj@<ecx>, IServiceProvider *pdispatchinfo)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x10088f10`
- `0x1009ee90`
- `0x100fe330`

## callees

- `0x1005064c`
- `0x10067bc0`
- `0x100753eb`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x10075417`
- `OLEAUT32!__imp__VariantInit@4` at `0x10075460`
- `OLEAUT32!__imp__VariantInit@4` at `0x10075417`
- `OLEAUT32!__imp__VariantInit@4` at `0x10075460`

## pseudocode

```c

```
