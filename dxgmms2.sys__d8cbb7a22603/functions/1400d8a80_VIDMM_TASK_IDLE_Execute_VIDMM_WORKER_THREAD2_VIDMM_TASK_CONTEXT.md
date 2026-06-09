# VIDMM_TASK_IDLE::Execute(VIDMM_WORKER_THREAD2 *,VIDMM_TASK_CONTEXT *)

- ea: `0x1400d8a80`
- end: `0x1400d8b69`
- name: `?Execute@VIDMM_TASK_IDLE@@UEAAJPEAUVIDMM_WORKER_THREAD2@@PEAUVIDMM_TASK_CONTEXT@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(VIDMM_TASK_IDLE *__hidden this, struct VIDMM_WORKER_THREAD2 *, struct VIDMM_TASK_CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x14002b730`
- `0x14002b830`
- `0x1400d8a80`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d8b2c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d8b2c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400d8b3d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400d8b3d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400d8af7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400d8af7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d8b03`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d8b03`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d8b20`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d8b20`

## pseudocode

```c

```
