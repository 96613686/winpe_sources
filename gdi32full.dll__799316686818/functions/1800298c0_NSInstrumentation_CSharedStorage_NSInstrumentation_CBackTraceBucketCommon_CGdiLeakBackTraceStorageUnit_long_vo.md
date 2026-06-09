# NSInstrumentation::CSharedStorage<NSInstrumentation::CBackTraceBucketCommon<CGdiLeakBackTraceStorageUnit>,long volatile,CGdiLeakBackTraceStorageUnit,NSInstrumentation::CBackTrace>::Remove(CGdiLeakBackTraceStorageUnit const * const)

- ea: `0x1800298c0`
- end: `0x180029972`
- name: `?Remove@?$CSharedStorage@V?$CBackTraceBucketCommon@VCGdiLeakBackTraceStorageUnit@@@NSInstrumentation@@$$CCJVCGdiLeakBackTraceStorageUnit@@VCBackTrace@2@@NSInstrumentation@@QEAA_NQEBVCGdiLeakBackTraceStorageUnit@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(NSInstrumentation::CPrioritizedWriterLock *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029af8`

## callees

- `0x1800298c0`
- `0x180029978`
- `0x1800299b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800298e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800298e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800298f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800298f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002991d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002991d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029939`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002995e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029939`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002995e`

## pseudocode

```c

```
