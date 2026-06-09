# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x100733b5`
- end: `0x10073501`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YGJPAVModuleBase@123@PAIABU_GUID@@PBUCreatorMap@123@PAPAUIUnknown@@@Z`
- size: `332`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::ModuleBase *modulePtr@<ecx>, unsigned int *flags@<edx>, const _GUID *riid, const Microsoft::WRL::Details::CreatorMap *entry, IUnknown **ppFactory)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10071a51`
- `0x10071b93`

## callees

- `0x10067b20`
- `0x100733b5`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x100733ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x100733ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x10073422`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x10073434`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x10073422`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x10073434`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1007347e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1007347e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x100734be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x100734be`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x10073490`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x10073490`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x100733fd`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1007349e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x100733fd`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1007349e`

## pseudocode

```c

```
