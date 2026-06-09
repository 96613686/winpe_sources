# CCache::AddElement(ulong,uchar *,ushort,ushort *,IUnknown *,IUnknown * *)

- ea: `0x180084b0c`
- end: `0x180084e89`
- name: `?AddElement@CCache@@QEAAJKPEAEGPEAGPEAUIUnknown@@PEAPEAU2@@Z`
- size: `893`
- prototype: `HRESULT __fastcall(CCache *this, unsigned int iHashValue, unsigned __int8 *pbKey, unsigned __int16 cbKey, unsigned __int16 *pfValueFlags, IUnknown *pUnknown, IUnknown **ppExistingUnknown)`
- caller_count: `7`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18004fa44`
- `0x18008490c`
- `0x1801150c0`
- `0x180120620`
- `0x180153870`
- `0x180154ce0`
- `0x18015f1c8`

## callees

- `0x18000b408`
- `0x180062084`
- `0x1800844b0`
- `0x180084b0c`
- `0x180084f7c`
- `0x180085a2c`
- `0x180087660`
- `0x18008db2c`
- `0x180184718`
- `0x18019a654`
- `0x1802135dd`
- `0x1802135e9`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180084cce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180084de0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180084cce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180084de0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084db5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084db5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084d00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084d44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084df6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084e5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084d00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084d44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084df6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084e5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180084be9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180084be9`

## string_xrefs

- `0x180084ba7`: `onecore\com\combase\catalog\cache.cxx`
- `0x180084b8e`: `Failed to initialize cache eviction state: %!HRESULT!`
- `0x180084ba0`: `CCache::AddElement`

## pseudocode

```c

```
