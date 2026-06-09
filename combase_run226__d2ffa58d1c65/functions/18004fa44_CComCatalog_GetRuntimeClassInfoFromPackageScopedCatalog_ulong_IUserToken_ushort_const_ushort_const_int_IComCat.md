# CComCatalog::GetRuntimeClassInfoFromPackageScopedCatalog(ulong,IUserToken *,ushort const *,ushort const *,int,IComCatalogInternal *,CCache *,_GUID const &,void * *,IComCatalogSCM *)

- ea: `0x18004fa44`
- end: `0x18004fec5`
- name: `?GetRuntimeClassInfoFromPackageScopedCatalog@CComCatalog@@AEAAJKPEAUIUserToken@@PEBG1HPEAUIComCatalogInternal@@PEAVCCache@@AEBU_GUID@@PEAPEAXPEAUIComCatalogSCM@@@Z`
- size: `1153`
- prototype: `HRESULT __fastcall(CComCatalog *this, unsigned int flags, IUserToken *pUserToken, const wchar_t *activatableClassId, const wchar_t *suppliedPackageMoniker, int explicitlyAllowPrivate, IComCatalogInternal *pCatalog, CCache *pCache, const _GUID *riid, void **ppv, IComCatalogSCM *flags)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180120620`

## callees

- `0x18000712c`
- `0x18003a8bc`
- `0x18004fa44`
- `0x18004fecc`
- `0x18005c640`
- `0x180084b0c`
- `0x180085170`
- `0x180085640`
- `0x1800859ec`
- `0x18008db2c`
- `0x1800a6f50`
- `0x18017ce74`
- `0x18017d00c`
- `0x18018a678`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fc05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fdea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fc05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fdea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004faf9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004faf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fbee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fcf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fdd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18024718f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fbee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fcf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fdd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18024718f`

## string_xrefs

- `0x18004fe32`: `onecore\com\combase\catalog\catalog.cxx`
- `0x18004fe5c`: `onecore\com\combase\catalog\catalog.cxx`
- `0x18004fe1a`: `onecore\com\combase\catalog\services.cxx`

## pseudocode

```c

```
