# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180084070`
- end: `0x1800841ff`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::ModuleBase *modulePtr, unsigned int *flags, const _GUID *riid, const Microsoft::WRL::Details::CreatorMap *entry, IUnknown **ppFactory)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180083ef8`
- `0x1800d199c`

## callees

- `0x180084070`
- `0x1800d3710`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800841b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800841b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180084101`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180084116`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180084101`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180084116`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800840c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800840c0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18008417c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18008417c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800840d2`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18008418b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800840d2`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18008418b`

## pseudocode

```c

```
