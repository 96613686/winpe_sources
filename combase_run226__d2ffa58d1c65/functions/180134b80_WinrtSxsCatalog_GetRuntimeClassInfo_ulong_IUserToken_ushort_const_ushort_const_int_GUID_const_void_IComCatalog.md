# WinrtSxsCatalog::GetRuntimeClassInfo(ulong,IUserToken *,ushort const *,ushort const *,int,_GUID const &,void * *,IComCatalogSCM *)

- ea: `0x180134b80`
- end: `0x180134e40`
- name: `?GetRuntimeClassInfo@WinrtSxsCatalog@@UEAAJKPEAUIUserToken@@PEBG1HAEBU_GUID@@PEAPEAXPEAUIComCatalogSCM@@@Z`
- size: `704`
- prototype: `HRESULT __fastcall(WinrtSxsCatalog *this, unsigned int flags, IUserToken *pUserToken, const wchar_t *activatableClassId, const wchar_t *packageMoniker, int __formal, const _GUID *riid, void **ppv, IComCatalogSCM *__formal)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18003a8bc`
- `0x18003c7ec`
- `0x180041c90`
- `0x1800450a0`
- `0x180134b80`
- `0x180134e48`
- `0x18019a654`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134be1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180134c80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180134c80`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180134e0b`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180134e16`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180134e1e`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180134e35`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180134e0b`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180134e16`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180134e1e`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180134e35`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x180134bd7`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x180134bd7`

## string_xrefs

- `0x180134c1e`: `onecore\com\combase\catalog\winrtsxscatalog.cpp`
- `0x180134cd9`: `onecore\com\combase\catalog\winrtsxscatalog.cpp`
- `0x180134d1c`: `onecore\com\combase\catalog\winrtsxscatalog.cpp`
- `0x180134d86`: `onecore\com\combase\catalog\winrtsxscatalog.cpp`
- `0x180134db5`: `onecore\com\combase\catalog\winrtsxscatalog.cpp`
- `0x180134dda`: `onecore\com\combase\catalog\winrtsxscatalog.cpp`

## pseudocode

```c

```
