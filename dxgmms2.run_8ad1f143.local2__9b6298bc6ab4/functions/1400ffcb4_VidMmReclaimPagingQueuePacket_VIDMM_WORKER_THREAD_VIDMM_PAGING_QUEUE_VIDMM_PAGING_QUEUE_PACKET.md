# VidMmReclaimPagingQueuePacket(VIDMM_WORKER_THREAD *,VIDMM_PAGING_QUEUE *,VIDMM_PAGING_QUEUE_PACKET *)

- ea: `0x1400ffcb4`
- end: `0x1400ffdf0`
- name: `?VidMmReclaimPagingQueuePacket@@YAXPEAUVIDMM_WORKER_THREAD@@PEAUVIDMM_PAGING_QUEUE@@PEAUVIDMM_PAGING_QUEUE_PACKET@@@Z`
- size: `316`
- prototype: `void __fastcall(struct VIDMM_WORKER_THREAD *, struct VIDMM_PAGING_QUEUE *, struct VIDMM_PAGING_QUEUE_PACKET *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400ad320`
- `0x1400d10f0`
- `0x1400e3b90`

## callees

- `0x140034800`
- `0x140045000`
- `0x1400ffcb4`
- `0x1400ffdf8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ffccd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ffccd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ffcde`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ffcde`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ffd6a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ffd6a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ffd76`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ffd76`
- `watchdog!WdLogSingleEntry5` at `0x1400ffdce`
- `watchdog!WdLogSingleEntry5` at `0x1400ffdce`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400ffda5`

## pseudocode

```c

```
