# NSInstrumentation::CSharedStorage<NSInstrumentation::CBackTraceBucketCommon<CGdiLeakBackTraceStorageUnit>,long volatile,CGdiLeakBackTraceStorageUnit,NSInstrumentation::CBackTrace>::Insert(NSInstrumentation::CBackTrace const * const)

- ea: `0x180029068`
- end: `0x180029147`
- name: `?Insert@?$CSharedStorage@V?$CBackTraceBucketCommon@VCGdiLeakBackTraceStorageUnit@@@NSInstrumentation@@$$CCJVCGdiLeakBackTraceStorageUnit@@VCBackTrace@2@@NSInstrumentation@@QEAAPEAVCGdiLeakBackTraceStorageUnit@@QEBVCBackTrace@2@@Z`
- size: `223`
- prototype: `__int64 __fastcall(NSInstrumentation::CPrioritizedWriterLock *this, NSInstrumentation::CBackTrace *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180027648`
- `0x1800786e8`

## callees

- `0x180029068`
- `0x180029978`
- `0x18002a288`
- `0x18002a3c4`
- `0x18002a3f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002908d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002908d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029096`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029096`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800290c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800290c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800290eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029133`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800290eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029133`

## pseudocode

```c

```
