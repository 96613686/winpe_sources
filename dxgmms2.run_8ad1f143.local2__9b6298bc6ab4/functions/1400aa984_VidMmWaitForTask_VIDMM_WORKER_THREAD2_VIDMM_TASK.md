# VidMmWaitForTask(VIDMM_WORKER_THREAD2 *,VIDMM_TASK *)

- ea: `0x1400aa984`
- end: `0x1400aaa4d`
- name: `?VidMmWaitForTask@@YAXPEAUVIDMM_WORKER_THREAD2@@PEAUVIDMM_TASK@@@Z`
- size: `201`
- prototype: `void __fastcall(struct VIDMM_WORKER_THREAD2 *, struct VIDMM_TASK *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400aa854`
- `0x1400e0378`

## callees

- `0x14002e850`
- `0x14002e950`
- `0x1400aa984`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400aa9bf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400aa9bf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400aa9cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400aa9cb`
- `ntoskrnl!KeInitializeEvent` at `0x1400aa9f2`
- `ntoskrnl!KeInitializeEvent` at `0x1400aa9f2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400aaa30`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400aaa30`

## pseudocode

```c

```
