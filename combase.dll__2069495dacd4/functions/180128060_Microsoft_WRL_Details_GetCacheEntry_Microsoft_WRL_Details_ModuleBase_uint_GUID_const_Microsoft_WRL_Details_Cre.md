# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180128060`
- end: `0x1801281e9`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `393`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::ModuleBase *modulePtr, unsigned int *flags, const _GUID *entry, const Microsoft::WRL::Details::CreatorMap *ppFactory, IUnknown **modulePtr)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180058fdc`

## callees

- `0x180128060`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18012817a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18012817a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18012814c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18012814c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801280f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801281ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801280f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801281ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801280b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801280b2`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1801280c8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180128194`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1801280c8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180128194`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180128165`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180128165`

## pseudocode

```c

```
