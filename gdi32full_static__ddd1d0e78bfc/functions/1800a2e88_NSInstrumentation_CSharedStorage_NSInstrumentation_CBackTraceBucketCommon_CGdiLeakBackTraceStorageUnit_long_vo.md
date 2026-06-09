# NSInstrumentation::CSharedStorage<NSInstrumentation::CBackTraceBucketCommon<CGdiLeakBackTraceStorageUnit>,long volatile,CGdiLeakBackTraceStorageUnit,NSInstrumentation::CBackTrace>::Enumerate<void (*)(void *,void *,void *)>(void (*)(void *,void *,void *),void *)

- ea: `0x1800a2e88`
- end: `0x1800a2f5c`
- name: `??$Enumerate@P6AXPEAX00@Z@?$CSharedStorage@V?$CBackTraceBucketCommon@VCGdiLeakBackTraceStorageUnit@@@NSInstrumentation@@$$CCJVCGdiLeakBackTraceStorageUnit@@VCBackTrace@2@@NSInstrumentation@@QEAAXP6AXPEAX00@Z0@Z`
- size: `212`
- prototype: `__int64 __fastcall(NSInstrumentation::CPrioritizedWriterLock *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a3b44`

## callees

- `0x180033140`
- `0x1800a2e88`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a2eba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a2ef9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a2eba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a2ef9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a2ec9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a2f2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a2ec9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a2f2e`

## pseudocode

```c

```
