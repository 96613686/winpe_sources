# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1801e3c50`
- end: `0x1801e3e06`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `438`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801e2c68`

## callees

- `0x1801e3c50`
- `0x1801e4f94`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801e3ca6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801e3ca6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801e3cf4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801e3d0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801e3cf4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801e3d0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801e3db3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801e3db3`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1801e3d76`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1801e3d76`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1801e3cbe`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1801e3d8b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1801e3cbe`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1801e3d8b`

## pseudocode

```c

```
