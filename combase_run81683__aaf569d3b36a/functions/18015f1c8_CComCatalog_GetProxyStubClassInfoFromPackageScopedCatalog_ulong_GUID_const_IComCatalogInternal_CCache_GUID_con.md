# CComCatalog::GetProxyStubClassInfoFromPackageScopedCatalog(ulong,_GUID const &,IComCatalogInternal *,CCache *,_GUID const &,void * *)

- ea: `0x18015f1c8`
- end: `0x18015f5e8`
- name: `?GetProxyStubClassInfoFromPackageScopedCatalog@CComCatalog@@AEAAJKAEBU_GUID@@PEAUIComCatalogInternal@@PEAVCCache@@0PEAPEAX@Z`
- size: `1056`
- prototype: `HRESULT __fastcall(CComCatalog *this, unsigned int flags, const _GUID *rclsid, IComCatalogInternal *pCatalog, CCache *pCache, const _GUID *riid, void **ppv)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180195ef4`

## callees

- `0x18000712c`
- `0x18003a8bc`
- `0x18003d1b0`
- `0x18004fecc`
- `0x18005c640`
- `0x180084b0c`
- `0x180085170`
- `0x180085640`
- `0x1800859ec`
- `0x1800a6f50`
- `0x18015f1c8`
- `0x18017ce74`
- `0x18017d00c`
- `0x1801999b0`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18015f5b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18015f5b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18015f33f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18015f33f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015f516`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015f547`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015f564`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015f598`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015f516`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015f547`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015f564`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015f598`

## string_xrefs

- `0x18015f2c4`: `onecore\com\combase\catalog\catalog.cxx`
- `0x18015f276`: `onecore\com\combase\catalog\services.cxx`

## pseudocode

```c

```
