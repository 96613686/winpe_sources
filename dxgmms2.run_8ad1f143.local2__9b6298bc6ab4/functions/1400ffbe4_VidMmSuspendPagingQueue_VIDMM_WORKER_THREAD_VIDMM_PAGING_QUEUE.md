# VidMmSuspendPagingQueue(VIDMM_WORKER_THREAD *,VIDMM_PAGING_QUEUE *)

- ea: `0x1400ffbe4`
- end: `0x1400ffcac`
- name: `?VidMmSuspendPagingQueue@@YAXPEAUVIDMM_WORKER_THREAD@@PEAUVIDMM_PAGING_QUEUE@@@Z`
- size: `200`
- prototype: `void __fastcall(struct VIDMM_WORKER_THREAD *, struct VIDMM_PAGING_QUEUE *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400ffb48`

## callees

- `0x14002e850`
- `0x14002e950`
- `0x1400d1e50`
- `0x1400ffbe4`
- `0x1400ffdf8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ffc00`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ffc00`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ffc11`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ffc11`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ffc54`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ffc54`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ffc60`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ffc60`

## pseudocode

```c

```
