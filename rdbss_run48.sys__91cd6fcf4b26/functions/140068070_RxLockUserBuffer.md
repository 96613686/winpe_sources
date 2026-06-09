# RxLockUserBuffer

- ea: `0x140068070`
- end: `0x140068324`
- name: `RxLockUserBuffer`
- size: `692`
- prototype: `void __stdcall(PRX_CONTEXT RxContext, PIRP Irp, LOCK_OPERATION Operation, ULONG BufferLength)`
- caller_count: `10`
- callee_count: `9`
- tags: ``

## callers

- `0x140010210`
- `0x140011eb0`
- `0x1400122f0`
- `0x140017540`
- `0x140018fb0`
- `0x140019170`
- `0x1400192d0`
- `0x140067ad0`
- `0x140068570`
- `0x140068e90`

## callees

- `0x1400104f0`
- `0x140010660`
- `0x140012320`
- `0x140016e20`
- `0x140016e70`
- `0x14001810c`
- `0x140024488`
- `0x140025d00`
- `0x140068070`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1400681ba`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1400681ba`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006814a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006814a`

## pseudocode

```c

```
