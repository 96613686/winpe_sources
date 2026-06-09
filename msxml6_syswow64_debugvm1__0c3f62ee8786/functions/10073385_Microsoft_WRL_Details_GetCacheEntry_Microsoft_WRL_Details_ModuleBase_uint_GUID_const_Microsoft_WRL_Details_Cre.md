# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x10073385`
- end: `0x100734d1`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YGJPAVModuleBase@123@PAIABU_GUID@@PBUCreatorMap@123@PAPAUIUnknown@@@Z`
- size: `332`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::ModuleBase *modulePtr@<ecx>, unsigned int *flags@<edx>, const _GUID *riid, const Microsoft::WRL::Details::CreatorMap *entry, IUnknown **ppFactory)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10071af1`
- `0x10071c33`

## callees

- `0x10067bc0`
- `0x10073385`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x100733bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x100733bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x100733f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x10073404`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x100733f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x10073404`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1007344e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1007344e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1007348e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1007348e`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x10073460`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x10073460`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x100733cd`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1007346e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x100733cd`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1007346e`

## pseudocode

```c

```
