# NSInstrumentation::CSharedStorage<NSInstrumentation::CBackTraceBucketCommon<CGdiLeakBackTraceStorageUnit>,long volatile,CGdiLeakBackTraceStorageUnit,NSInstrumentation::CBackTrace>::Insert(NSInstrumentation::CBackTrace const * const)

- ea: `0x18003278c`
- end: `0x180032866`
- name: `?Insert@?$CSharedStorage@V?$CBackTraceBucketCommon@VCGdiLeakBackTraceStorageUnit@@@NSInstrumentation@@$$CCJVCGdiLeakBackTraceStorageUnit@@VCBackTrace@2@@NSInstrumentation@@QEAAPEAVCGdiLeakBackTraceStorageUnit@@QEBVCBackTrace@2@@Z`
- size: `218`
- prototype: `__int64 __fastcall(NSInstrumentation::CPrioritizedWriterLock *this, NSInstrumentation::CBackTrace *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180030910`
- `0x18007d1c8`

## callees

- `0x18003278c`
- `0x180033140`
- `0x180033af0`
- `0x180033b50`
- `0x180034094`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800327af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800327af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800327be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800327be`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800327f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800327f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032826`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003284c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032826`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003284c`

## pseudocode

```c

```
