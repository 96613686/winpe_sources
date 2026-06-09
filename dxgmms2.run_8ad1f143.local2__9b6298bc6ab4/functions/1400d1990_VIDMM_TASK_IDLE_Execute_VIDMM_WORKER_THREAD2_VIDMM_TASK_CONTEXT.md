# VIDMM_TASK_IDLE::Execute(VIDMM_WORKER_THREAD2 *,VIDMM_TASK_CONTEXT *)

- ea: `0x1400d1990`
- end: `0x1400d1a79`
- name: `?Execute@VIDMM_TASK_IDLE@@UEAAJPEAUVIDMM_WORKER_THREAD2@@PEAUVIDMM_TASK_CONTEXT@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(VIDMM_TASK_IDLE *__hidden this, struct VIDMM_WORKER_THREAD2 *, struct VIDMM_TASK_CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x14002e850`
- `0x14002e950`
- `0x1400d1990`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d1a3c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d1a3c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400d1a4d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400d1a4d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400d1a07`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400d1a07`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d1a13`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d1a13`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d1a30`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d1a30`

## pseudocode

```c

```
