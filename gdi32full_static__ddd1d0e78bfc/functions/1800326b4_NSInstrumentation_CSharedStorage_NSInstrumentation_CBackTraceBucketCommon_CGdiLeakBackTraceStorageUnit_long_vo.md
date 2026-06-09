# NSInstrumentation::CSharedStorage<NSInstrumentation::CBackTraceBucketCommon<CGdiLeakBackTraceStorageUnit>,long volatile,CGdiLeakBackTraceStorageUnit,NSInstrumentation::CBackTrace>::Lookup(NSInstrumentation::CBackTrace const * const)

- ea: `0x1800326b4`
- end: `0x180032784`
- name: `?Lookup@?$CSharedStorage@V?$CBackTraceBucketCommon@VCGdiLeakBackTraceStorageUnit@@@NSInstrumentation@@$$CCJVCGdiLeakBackTraceStorageUnit@@VCBackTrace@2@@NSInstrumentation@@QEBAPEAVCGdiLeakBackTraceStorageUnit@@QEBVCBackTrace@2@@Z`
- size: `208`
- prototype: `__int64 __fastcall(NSInstrumentation::CPrioritizedWriterLock *this, NSInstrumentation::CBackTrace *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180030910`
- `0x18007d1c8`

## callees

- `0x1800326b4`
- `0x180033140`
- `0x180033b50`
- `0x180034334`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800326d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003271e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800326d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003271e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800326e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180032744`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003276a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800326e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180032744`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003276a`

## pseudocode

```c

```
