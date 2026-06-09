# NSInstrumentation::CSharedStorage<NSInstrumentation::CBackTraceBucketCommon<CGdiLeakBackTraceStorageUnit>,long volatile,CGdiLeakBackTraceStorageUnit,NSInstrumentation::CBackTrace>::Remove(CGdiLeakBackTraceStorageUnit const * const)

- ea: `0x180033068`
- end: `0x180033139`
- name: `?Remove@?$CSharedStorage@V?$CBackTraceBucketCommon@VCGdiLeakBackTraceStorageUnit@@@NSInstrumentation@@$$CCJVCGdiLeakBackTraceStorageUnit@@VCBackTrace@2@@NSInstrumentation@@QEAA_NQEBVCGdiLeakBackTraceStorageUnit@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(NSInstrumentation::CPrioritizedWriterLock *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800332e0`

## callees

- `0x180033068`
- `0x180033140`
- `0x180033180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180033091`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180033091`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800330a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800330a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800330d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800330d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800330f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003311f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800330f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003311f`

## pseudocode

```c

```
