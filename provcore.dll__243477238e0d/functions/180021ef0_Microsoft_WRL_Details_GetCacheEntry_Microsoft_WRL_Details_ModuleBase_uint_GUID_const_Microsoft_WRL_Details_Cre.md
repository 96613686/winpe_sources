# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180021ef0`
- end: `0x18002208e`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `414`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::ModuleBase *modulePtr, unsigned int *flags, const _GUID *riid, const Microsoft::WRL::Details::CreatorMap *entry, IUnknown **ppFactory)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800218a0`
- `0x180021a18`

## callees

- `0x180002790`
- `0x180021ef0`
- `0x1800221d4`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021f8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021fa4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021f8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021fa4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002203b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002203b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021f51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021f51`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180021f63`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180022019`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180021f63`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180022019`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18002200a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18002200a`

## pseudocode

```c

```
