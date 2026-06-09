# FltGetTransactionContext

- ea: `0x180072570`
- end: `0x18007273c`
- name: `FltGetTransactionContext`
- size: `460`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE Instance, PKTRANSACTION Transaction, PFLT_CONTEXT *Context)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180013100`
- `0x180055440`
- `0x180055500`
- `0x180055840`
- `0x1800558d0`
- `0x180055960`
- `0x180055a00`
- `0x18007ee90`

## callees

- `0x1800139a0`
- `0x180072570`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x180072602`
- `ntoskrnl!KeBugCheckEx` at `0x1800726eb`
- `ntoskrnl!KeBugCheckEx` at `0x180072602`
- `ntoskrnl!KeBugCheckEx` at `0x1800726eb`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180072598`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180072682`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180072598`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180072682`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180072620`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180072655`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180072709`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18007271f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180072620`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180072655`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180072709`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18007271f`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1800725ad`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1800725ad`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x180072614`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x180072649`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x180072614`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x180072649`

## pseudocode

```c

```
