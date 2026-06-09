# CDownloadManager::GetJob(_GUID const &,std::shared_ptr<CBackgroundCopyJob> &)

- ea: `0x180096924`
- end: `0x180096a2e`
- name: `?GetJob@CDownloadManager@@QEAAJAEBU_GUID@@AEAV?$shared_ptr@VCBackgroundCopyJob@@@std@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800171c0`

## callees

- `0x18007ca54`
- `0x18007e3cc`
- `0x180096924`
- `0x180097408`
- `0x1800b11a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009695c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180096a0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009695c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180096a0c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180096987`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180096987`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800969e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800969e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180096940`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800969ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180096940`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800969ed`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180096a03`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180096a03`

## pseudocode

```c

```
