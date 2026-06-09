# CComSxSCatalog::GetClassInfoW(ulong,IUserToken *,_GUID const &,_GUID const &,void * *,void *)

- ea: `0x18013bac0`
- end: `0x18013bced`
- name: `?GetClassInfoW@CComSxSCatalog@@UEAAJKPEAUIUserToken@@AEBU_GUID@@1PEAPEAXPEAX@Z`
- size: `557`
- prototype: `HRESULT __fastcall(CComSxSCatalog *this, unsigned int dwFlags, IUserToken *__formal, const _GUID *guidConfiguredClsid, const _GUID *riid, void **ppv, void *__formal)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180152ae0`

## callees

- `0x18000712c`
- `0x18004768c`
- `0x180063c44`
- `0x180087534`
- `0x18008db2c`
- `0x18013bac0`
- `0x1801999b0`
- `0x18019a654`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013bb3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013bb3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013bbcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013bbcd`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18013bc0f`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18013bc50`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18013bc62`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18013bc0f`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18013bc50`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18013bc62`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionGuid` at `0x18013bb30`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionGuid` at `0x18013bb30`

## string_xrefs

- `0x18013bcb3`: `CLSID:%ws %!HRESULT!`
- `0x18013bca0`: `CComSxSCatalog::GetClassInfoW`
- `0x18013bcac`: `onecore\com\combase\catalog\sxscat.cxx`

## pseudocode

```c

```
