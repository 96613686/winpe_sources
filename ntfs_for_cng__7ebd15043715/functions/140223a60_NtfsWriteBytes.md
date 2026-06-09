# NtfsWriteBytes

- ea: `0x140223a60`
- end: `0x140223ffd`
- name: `NtfsWriteBytes`
- size: `1437`
- prototype: `void __fastcall(__int64, __int64, __int64, union _LARGE_INTEGER, char *Buffer, int, __int16)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x14015098c`
- `0x1401578a0`
- `0x14015f620`
- `0x1401700a0`
- `0x140226690`
- `0x14027e3c8`

## callees

- `0x1400055f0`
- `0x140007ea0`
- `0x14000c290`
- `0x140015b90`
- `0x140033250`
- `0x140037db4`
- `0x1400596c0`
- `0x140175a80`
- `0x140223a60`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140223f8c`
- `ntoskrnl!IoFreeIrp` at `0x1402b5d2e`
- `ntoskrnl!IoFreeIrp` at `0x140223f8c`
- `ntoskrnl!IoFreeIrp` at `0x1402b5d2e`
- `ntoskrnl!MmUnmapLockedPages` at `0x140223fd2`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402b5d55`
- `ntoskrnl!MmUnmapLockedPages` at `0x140223fd2`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402b5d55`
- `ntoskrnl!IoAllocateMdl` at `0x140223bdc`
- `ntoskrnl!IoAllocateMdl` at `0x140223bdc`
- `ntoskrnl!MmProbeAndLockPages` at `0x140223c02`
- `ntoskrnl!MmProbeAndLockPages` at `0x140223c02`
- `ntoskrnl!IoFreeMdl` at `0x140223c15`
- `ntoskrnl!IoFreeMdl` at `0x140223d3d`
- `ntoskrnl!IoFreeMdl` at `0x140223fbd`
- `ntoskrnl!IoFreeMdl` at `0x1402b5d1e`
- `ntoskrnl!IoFreeMdl` at `0x1402b5d65`
- `ntoskrnl!IoFreeMdl` at `0x1402cf12a`
- `ntoskrnl!IoFreeMdl` at `0x140223c15`
- `ntoskrnl!IoFreeMdl` at `0x140223d3d`
- `ntoskrnl!IoFreeMdl` at `0x140223fbd`
- `ntoskrnl!IoFreeMdl` at `0x1402b5d1e`
- `ntoskrnl!IoFreeMdl` at `0x1402b5d65`
- `ntoskrnl!IoFreeMdl` at `0x1402cf12a`
- `ntoskrnl!MmMdlPageContentsState` at `0x140223c90`
- `ntoskrnl!MmMdlPageContentsState` at `0x140223c90`
- `ntoskrnl!MmUnlockPages` at `0x140223d28`
- `ntoskrnl!MmUnlockPages` at `0x140223feb`
- `ntoskrnl!MmUnlockPages` at `0x1402b5d0d`
- `ntoskrnl!MmUnlockPages` at `0x140223d28`
- `ntoskrnl!MmUnlockPages` at `0x140223feb`
- `ntoskrnl!MmUnlockPages` at `0x1402b5d0d`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140223b58`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140223b58`

## pseudocode

```c

```
