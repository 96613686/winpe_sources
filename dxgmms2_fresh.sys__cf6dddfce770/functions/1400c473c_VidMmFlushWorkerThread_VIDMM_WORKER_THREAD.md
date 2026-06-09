# VidMmFlushWorkerThread(VIDMM_WORKER_THREAD *)

- ea: `0x1400c473c`
- end: `0x1400c482e`
- name: `?VidMmFlushWorkerThread@@YAXPEAUVIDMM_WORKER_THREAD@@@Z`
- size: `242`
- prototype: `void __fastcall(struct VIDMM_WORKER_THREAD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400b7da4`

## callees

- `0x140004268`
- `0x1400c473c`
- `0x1401206e8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c4750`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c4750`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c4761`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c4761`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c480a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c480a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c4816`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c4816`
- `watchdog!WdLogSingleEntry1` at `0x1400c47af`
- `watchdog!WdLogSingleEntry1` at `0x1400c47af`

## string_xrefs

- `0x1400c47c4`: `Worker thread must be in the running state in order to flush. CurrentStatus=%d.`

## pseudocode

```c

```
