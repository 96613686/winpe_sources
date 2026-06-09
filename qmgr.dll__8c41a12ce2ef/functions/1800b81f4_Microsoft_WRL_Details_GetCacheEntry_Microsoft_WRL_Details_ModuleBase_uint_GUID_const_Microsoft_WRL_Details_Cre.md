# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1800b81f4`
- end: `0x1800b837b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b7e38`

## callees

- `0x1800b81f4`
- `0x1800b83e8`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b8246`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b8246`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b8288`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b829d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b8288`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b829d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b832f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b832f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800b8258`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800b830d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800b8258`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800b830d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800b82fe`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800b82fe`

## pseudocode

```c

```
