# RefsDeleteScb

- ea: `0x1403113e4`
- end: `0x14031165b`
- name: `RefsDeleteScb`
- size: `631`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _SCB *)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14030ffc0`
- `0x140310460`
- `0x140311240`
- `0x14033d970`

## callees

- `0x140009aa0`
- `0x14004d0a0`
- `0x140090b40`
- `0x1400a5a70`
- `0x1400c8644`
- `0x14010e8f8`
- `0x1401100c4`
- `0x14028ddc0`
- `0x1403113e4`
- `0x140311d70`
- `0x140311df0`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x140311404`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140311428`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140311428`
- `ntoskrnl!FsRtlFreeFileLock` at `0x14031144c`
- `ntoskrnl!FsRtlFreeFileLock` at `0x14031144c`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14031156a`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14031156a`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14031157f`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14031157f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140311631`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140311631`
- `ntoskrnl!ExFreePoolWithTag` at `0x140311497`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403114d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140311644`
- `ntoskrnl!ExFreePoolWithTag` at `0x140311497`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403114d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140311644`

## pseudocode

```c

```
