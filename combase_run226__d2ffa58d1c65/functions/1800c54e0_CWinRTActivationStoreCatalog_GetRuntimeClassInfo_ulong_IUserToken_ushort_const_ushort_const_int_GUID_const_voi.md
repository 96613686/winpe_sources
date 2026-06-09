# CWinRTActivationStoreCatalog::GetRuntimeClassInfo(ulong,IUserToken *,ushort const *,ushort const *,int,_GUID const &,void * *,IComCatalogSCM *)

- ea: `0x1800c54e0`
- end: `0x1800c6081`
- name: `?GetRuntimeClassInfo@CWinRTActivationStoreCatalog@@UEAAJKPEAUIUserToken@@PEBG1HAEBU_GUID@@PEAPEAXPEAUIComCatalogSCM@@@Z`
- size: `2977`
- prototype: `HRESULT __fastcall(CWinRTActivationStoreCatalog *this, unsigned int flags, IUserToken *pUserToken, const wchar_t *activatableClassId, const wchar_t *packageMoniker, int allowPrivate, const _GUID *riid, void **ppv, IComCatalogSCM *pComCatalogCallback)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b408`
- `0x18001f124`
- `0x180041e50`
- `0x1800421e0`
- `0x1800436b0`
- `0x1800450a0`
- `0x180056f70`
- `0x1800572e4`
- `0x18005a0d0`
- `0x1800865f4`
- `0x180086714`
- `0x1800a4e24`
- `0x1800c43d0`
- `0x1800c54e0`
- `0x1800f5d34`
- `0x1801de718`
- `0x1802135e9`
- `0x180255010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800c5f22`
- `ntdll!RtlNtStatusToDosError` at `0x1800c5f7c`
- `ntdll!RtlNtStatusToDosError` at `0x1800c5f22`
- `ntdll!RtlNtStatusToDosError` at `0x1800c5f7c`
- `ntdll!RtlLoadString` at `0x1800c5f1a`
- `ntdll!RtlLoadString` at `0x1800c5f74`
- `ntdll!RtlLoadString` at `0x1800c5f1a`
- `ntdll!RtlLoadString` at `0x1800c5f74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c562a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c581b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c59e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c5d85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c562a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c581b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c59e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c5d85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c561c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c580d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c561c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c580d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c578d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c578d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c5740`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c5740`

## string_xrefs

- `0x1800c553d`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1800c5b95`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1800c5d32`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1800c5bba`: `Look up ActivatableClassId entry %ws for package %ws in scope %!Windows::Foundation::RegistrationScope!: %!HRESULT!`
- `0x1800c5d48`: `Look up ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!: %!HRESULT!`

## pseudocode

```c

```
