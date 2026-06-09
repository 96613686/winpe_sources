# DXGFASTMUTEX::Acquire(void)

- ea: `0x14002d8cc`
- end: `0x14002da89`
- name: `?Acquire@DXGFASTMUTEX@@QEAAXXZ`
- size: `445`
- prototype: `void __fastcall(DXGFASTMUTEX *__hidden this)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x14002d810`
- `0x14009e984`
- `0x1400aad90`
- `0x1400ac018`
- `0x1400ad5a0`
- `0x1400b02e4`
- `0x1400b7298`
- `0x1400ba108`
- `0x1400c4984`
- `0x1400d0a94`
- `0x1400d4614`
- `0x1400d6850`
- `0x1400d6b24`
- `0x1400dadac`
- `0x1400e4098`
- `0x1400e8048`
- `0x1400e9544`
- `0x1400efba8`
- `0x1400f24e0`
- `0x1400f52b4`
- `0x1400feb90`
- `0x1401056b0`
- `0x14010f2ec`
- `0x14011babc`
- `0x14011bb88`
- `0x14011c13c`

## callees

- `0x140004268`
- `0x1400128c8`
- `0x14002d8cc`

## import_xrefs

- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14002d916`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14002d916`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002d8d9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002d8d9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002d939`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002d939`
- `watchdog!WdLogSingleEntry0` at `0x14002d998`
- `watchdog!WdLogSingleEntry0` at `0x14002d9ea`
- `watchdog!WdLogSingleEntry0` at `0x14002da3c`
- `watchdog!WdLogSingleEntry0` at `0x14002d998`
- `watchdog!WdLogSingleEntry0` at `0x14002d9ea`
- `watchdog!WdLogSingleEntry0` at `0x14002da3c`

## string_xrefs

- `0x14002d9ff`: `NULL == m_OwningThread`

## pseudocode

```c

```
