# DXGFASTMUTEX::Acquire(void)

- ea: `0x14002fbac`
- end: `0x14002fd69`
- name: `?Acquire@DXGFASTMUTEX@@QEAAXXZ`
- size: `445`
- prototype: `void __fastcall(DXGFASTMUTEX *__hidden this)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x14002faf0`
- `0x14009ae3c`
- `0x1400a9c40`
- `0x1400aafd0`
- `0x1400ac1f0`
- `0x1400aed94`
- `0x1400b395c`
- `0x1400b6730`
- `0x1400c0894`
- `0x1400cab84`
- `0x1400ce4b0`
- `0x1400cfac0`
- `0x1400cfd94`
- `0x1400d2abc`
- `0x1400dbc38`
- `0x1400dfbe8`
- `0x1400e1530`
- `0x1400e765c`
- `0x1400e84b4`
- `0x1400f02d4`
- `0x1400fe1f4`
- `0x14010416c`
- `0x14010b6d4`
- `0x140117fbc`
- `0x140118088`
- `0x140118600`

## callees

- `0x1400045ec`
- `0x140012e28`
- `0x14002fbac`

## import_xrefs

- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14002fbf6`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14002fbf6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002fbb9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002fbb9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002fc19`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002fc19`
- `watchdog!WdLogSingleEntry0` at `0x14002fc78`
- `watchdog!WdLogSingleEntry0` at `0x14002fcca`
- `watchdog!WdLogSingleEntry0` at `0x14002fd1c`
- `watchdog!WdLogSingleEntry0` at `0x14002fc78`
- `watchdog!WdLogSingleEntry0` at `0x14002fcca`
- `watchdog!WdLogSingleEntry0` at `0x14002fd1c`

## string_xrefs

- `0x14002fcdf`: `NULL == m_OwningThread`

## pseudocode

```c

```
