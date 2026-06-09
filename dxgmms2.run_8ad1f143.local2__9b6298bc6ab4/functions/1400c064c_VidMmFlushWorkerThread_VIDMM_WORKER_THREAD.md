# VidMmFlushWorkerThread(VIDMM_WORKER_THREAD *)

- ea: `0x1400c064c`
- end: `0x1400c073e`
- name: `?VidMmFlushWorkerThread@@YAXPEAUVIDMM_WORKER_THREAD@@@Z`
- size: `242`
- prototype: `void __fastcall(struct VIDMM_WORKER_THREAD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400b4468`

## callees

- `0x1400045ec`
- `0x1400c064c`
- `0x14011cf10`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c0660`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c0660`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c0671`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c0671`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c071a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c071a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c0726`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c0726`
- `watchdog!WdLogSingleEntry1` at `0x1400c06bf`
- `watchdog!WdLogSingleEntry1` at `0x1400c06bf`

## string_xrefs

- `0x1400c06d4`: `Worker thread must be in the running state in order to flush. CurrentStatus=%d.`

## pseudocode

```c

```
