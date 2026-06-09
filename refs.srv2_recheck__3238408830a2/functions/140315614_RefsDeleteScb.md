# RefsDeleteScb

- ea: `0x140315614`
- end: `0x14031588b`
- name: `RefsDeleteScb`
- size: `631`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _SCB *)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x1403141f0`
- `0x140314690`
- `0x140315470`
- `0x1403407b0`

## callees

- `0x140035da0`
- `0x14008a530`
- `0x14008b590`
- `0x14009fca0`
- `0x1400cedec`
- `0x140113068`
- `0x140114834`
- `0x140294d54`
- `0x140315614`
- `0x140315fa0`
- `0x140316020`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x140315634`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140315658`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140315658`
- `ntoskrnl!FsRtlFreeFileLock` at `0x14031567c`
- `ntoskrnl!FsRtlFreeFileLock` at `0x14031567c`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14031579a`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14031579a`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x1403157af`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x1403157af`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140315861`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140315861`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403156c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140315706`
- `ntoskrnl!ExFreePoolWithTag` at `0x140315874`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403156c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140315706`
- `ntoskrnl!ExFreePoolWithTag` at `0x140315874`

## pseudocode

```c

```
