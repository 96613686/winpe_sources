# CDefObject::Create(IUnknown *,_GUID const &,ulong,IClassFactory *)

- ea: `0x18004b038`
- end: `0x18004b296`
- name: `?Create@CDefObject@@SAPEAUIUnknown@@PEAU2@AEBU_GUID@@KPEAUIClassFactory@@@Z`
- size: `606`
- prototype: `IUnknown *__fastcall(IUnknown *pUnkOuter, const _GUID *clsid, unsigned int flags, IClassFactory *pCF)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004af70`
- `0x180098920`

## callees

- `0x18002b1b4`
- `0x18004b038`
- `0x18004de7c`
- `0x1800974a8`
- `0x1800c42b8`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b0a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b1ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b0a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b1ff`
- `api-ms-win-core-com-private-l1-1-0!InternalCreateCAggId` at `0x18004b07c`
- `api-ms-win-core-com-private-l1-1-0!InternalCreateCAggId` at `0x18004b07c`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18004b06a`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18004b06a`
- `api-ms-win-core-com-private-l1-1-1!InternalCAggIdRelease` at `0x18004b26e`
- `api-ms-win-core-com-private-l1-1-1!InternalCAggIdRelease` at `0x18004b26e`
- `api-ms-win-core-com-private-l1-1-1!InternalCAggIdSetHandler` at `0x18004b115`
- `api-ms-win-core-com-private-l1-1-1!InternalCAggIdSetHandler` at `0x18004b115`

## pseudocode

```c

```
