# VidMmWaitForTask(VIDMM_WORKER_THREAD2 *,VIDMM_TASK *)

- ea: `0x1400abac4`
- end: `0x1400abb8d`
- name: `?VidMmWaitForTask@@YAXPEAUVIDMM_WORKER_THREAD2@@PEAUVIDMM_TASK@@@Z`
- size: `201`
- prototype: `void __fastcall(struct VIDMM_WORKER_THREAD2 *, struct VIDMM_TASK *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400ab994`
- `0x1400e87d8`

## callees

- `0x14002b730`
- `0x14002b830`
- `0x1400abac4`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400abaff`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400abaff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400abb0b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400abb0b`
- `ntoskrnl!KeInitializeEvent` at `0x1400abb32`
- `ntoskrnl!KeInitializeEvent` at `0x1400abb32`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400abb70`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400abb70`

## pseudocode

```c

```
