# NSInstrumentation::CSharedStorage<NSInstrumentation::CBackTraceBucketCommon<CGdiLeakBackTraceStorageUnit>,long volatile,CGdiLeakBackTraceStorageUnit,NSInstrumentation::CBackTrace>::Lookup(NSInstrumentation::CBackTrace const * const)

- ea: `0x180028fb0`
- end: `0x180029061`
- name: `?Lookup@?$CSharedStorage@V?$CBackTraceBucketCommon@VCGdiLeakBackTraceStorageUnit@@@NSInstrumentation@@$$CCJVCGdiLeakBackTraceStorageUnit@@VCBackTrace@2@@NSInstrumentation@@QEBAPEAVCGdiLeakBackTraceStorageUnit@@QEBVCBackTrace@2@@Z`
- size: `177`
- prototype: `__int64 __fastcall(NSInstrumentation::CPrioritizedWriterLock *this, NSInstrumentation::CBackTrace *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180027648`
- `0x1800786e8`

## callees

- `0x180028fb0`
- `0x180029978`
- `0x18002a3f4`
- `0x18002a940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180028fd3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002900e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180028fd3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002900e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028fdc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002902e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002904d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028fdc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002902e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002904d`

## pseudocode

```c

```
