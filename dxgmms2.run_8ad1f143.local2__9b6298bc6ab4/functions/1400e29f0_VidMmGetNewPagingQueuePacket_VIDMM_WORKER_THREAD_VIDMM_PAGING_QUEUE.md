# VidMmGetNewPagingQueuePacket(VIDMM_WORKER_THREAD *,VIDMM_PAGING_QUEUE *)

- ea: `0x1400e29f0`
- end: `0x1400e2acf`
- name: `?VidMmGetNewPagingQueuePacket@@YAPEAUVIDMM_PAGING_QUEUE_PACKET@@PEAUVIDMM_WORKER_THREAD@@PEAUVIDMM_PAGING_QUEUE@@@Z`
- size: `223`
- prototype: `struct VIDMM_PAGING_QUEUE_PACKET *__fastcall(struct VIDMM_WORKER_THREAD *, struct VIDMM_PAGING_QUEUE *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400e1530`
- `0x1400e2504`
- `0x1400e34ac`

## callees

- `0x1400037a0`
- `0x140058ac0`
- `0x1400e29f0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e2a03`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e2a03`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e2a14`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e2a14`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e2a63`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e2a63`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e2a6f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e2a6f`

## pseudocode

```c

```
