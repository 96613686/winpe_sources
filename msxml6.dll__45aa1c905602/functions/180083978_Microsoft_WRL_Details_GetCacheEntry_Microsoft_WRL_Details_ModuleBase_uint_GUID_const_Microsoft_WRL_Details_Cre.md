# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180083978`
- end: `0x180083b36`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `446`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::ModuleBase *modulePtr, unsigned int *flags, const _GUID *riid, const Microsoft::WRL::Details::CreatorMap *entry, IUnknown **ppFactory)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800837e0`
- `0x1800d355c`

## callees

- `0x180083978`
- `0x1800d5310`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083ae0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083ae0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180083a19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180083a34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180083a19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180083a34`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800839cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800839cc`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180083aa0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180083aa0`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800839e4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180083ab5`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800839e4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180083ab5`

## pseudocode

```c

```
