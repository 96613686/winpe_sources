# VidMmReclaimPagingQueuePacket(VIDMM_WORKER_THREAD *,VIDMM_PAGING_QUEUE *,VIDMM_PAGING_QUEUE_PACKET *)

- ea: `0x1400eb3fc`
- end: `0x1400eb538`
- name: `?VidMmReclaimPagingQueuePacket@@YAXPEAUVIDMM_WORKER_THREAD@@PEAUVIDMM_PAGING_QUEUE@@PEAUVIDMM_PAGING_QUEUE_PACKET@@@Z`
- size: `316`
- prototype: `void __fastcall(struct VIDMM_WORKER_THREAD *, struct VIDMM_PAGING_QUEUE *, struct VIDMM_PAGING_QUEUE_PACKET *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400ae7e0`
- `0x1400d81e0`
- `0x1400ec6c0`

## callees

- `0x1400330f0`
- `0x140045200`
- `0x1400eb3fc`
- `0x1400eb540`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400eb415`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400eb415`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400eb426`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400eb426`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400eb4b2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400eb4b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400eb4be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400eb4be`
- `watchdog!WdLogSingleEntry5` at `0x1400eb516`
- `watchdog!WdLogSingleEntry5` at `0x1400eb516`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400eb4ed`

## pseudocode

```c

```
