# NSInstrumentation::CSharedStorage<NSInstrumentation::CBackTraceBucketCommon<CGdiLeakBackTraceStorageUnit>,long volatile,CGdiLeakBackTraceStorageUnit,NSInstrumentation::CBackTrace>::Enumerate<void (*)(void *,void *,void *)>(void (*)(void *,void *,void *),void *)

- ea: `0x18009fe50`
- end: `0x18009ff0b`
- name: `??$Enumerate@P6AXPEAX00@Z@?$CSharedStorage@V?$CBackTraceBucketCommon@VCGdiLeakBackTraceStorageUnit@@@NSInstrumentation@@$$CCJVCGdiLeakBackTraceStorageUnit@@VCBackTrace@2@@NSInstrumentation@@QEAAXP6AXPEAX00@Z0@Z`
- size: `187`
- prototype: `__int64 __fastcall(NSInstrumentation::CPrioritizedWriterLock *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a0aa8`

## callees

- `0x180029978`
- `0x18009fe50`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009fe82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009feb5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009fe82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009feb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009fe8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009fee4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009fe8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009fee4`

## pseudocode

```c

```
