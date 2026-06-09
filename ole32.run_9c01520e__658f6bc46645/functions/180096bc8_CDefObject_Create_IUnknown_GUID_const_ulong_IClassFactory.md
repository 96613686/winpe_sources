# CDefObject::Create(IUnknown *,_GUID const &,ulong,IClassFactory *)

- ea: `0x180096bc8`
- end: `0x180096e6a`
- name: `?Create@CDefObject@@SAPEAUIUnknown@@PEAU2@AEBU_GUID@@KPEAUIClassFactory@@@Z`
- size: `674`
- prototype: `IUnknown *__fastcall(IUnknown *pUnkOuter, const _GUID *clsid, unsigned int flags, IClassFactory *pCF)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180099e00`
- `0x18009eb90`

## callees

- `0x18002fa3c`
- `0x1800808d8`
- `0x1800964c4`
- `0x180096bc8`
- `0x1800ce50c`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180096c55`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180096da2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180096c55`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180096da2`
- `api-ms-win-core-com-private-l1-1-0!InternalCreateCAggId` at `0x180096c21`
- `api-ms-win-core-com-private-l1-1-0!InternalCreateCAggId` at `0x180096c21`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x180096c09`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x180096c09`
- `api-ms-win-core-com-private-l1-1-1!InternalCAggIdSetHandler` at `0x180096ca6`
- `api-ms-win-core-com-private-l1-1-1!InternalCAggIdSetHandler` at `0x180096ca6`
- `api-ms-win-core-com-private-l1-1-1!InternalCAggIdRelease` at `0x180096e3e`
- `api-ms-win-core-com-private-l1-1-1!InternalCAggIdRelease` at `0x180096e3e`

## pseudocode

```c

```
