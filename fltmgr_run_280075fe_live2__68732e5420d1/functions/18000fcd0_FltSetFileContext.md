# FltSetFileContext

- ea: `0x18000fcd0`
- end: `0x18000ff60`
- name: `FltSetFileContext`
- size: `656`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, FLT_SET_CONTEXT_OPERATION Operation, PFLT_CONTEXT NewContext, PFLT_CONTEXT *OldContext)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180080500`

## callees

- `0x1800085f0`
- `0x180009f20`
- `0x18000d090`
- `0x18000fcd0`
- `0x18000ff70`
- `0x180010150`
- `0x180010400`
- `0x180010500`
- `0x180010540`
- `0x180010ab0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x18000fef7`
- `ntoskrnl!KeBugCheckEx` at `0x18000fef7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18000fda9`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18000fda9`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000fe32`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000fe5b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000fe32`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000fe5b`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18000fdbb`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18000fdbb`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000fe26`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000fe4f`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000fe26`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000fe4f`

## pseudocode

```c

```
