# FltDeleteInstanceContext

- ea: `0x1800117c0`
- end: `0x1800118b0`
- name: `FltDeleteInstanceContext`
- size: `240`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE Instance, PFLT_CONTEXT *OldContext)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180063b40`
- `0x18007e370`

## callees

- `0x180010ab0`
- `0x1800117c0`
- `0x18005dcc0`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1800117d8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1800117d8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001181a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180011857`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001181a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180011857`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1800117ed`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1800117ed`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18001180e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18001184b`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18001180e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18001184b`

## pseudocode

```c

```
