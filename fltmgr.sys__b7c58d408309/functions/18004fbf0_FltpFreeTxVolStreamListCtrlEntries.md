# FltpFreeTxVolStreamListCtrlEntries

- ea: `0x18004fbf0`
- end: `0x18004fc9a`
- name: `FltpFreeTxVolStreamListCtrlEntries`
- size: `170`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18004eac0`
- `0x180070b30`

## callees

- `0x18000f5b0`
- `0x180012d80`
- `0x18004fbf0`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x18004fc02`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18004fc02`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18004fc4d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18004fc4d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18004fc75`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18004fc75`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18004fc1a`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18004fc1a`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18004fc41`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18004fc41`

## pseudocode

```c

```
