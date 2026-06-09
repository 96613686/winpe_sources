# NtfsWriteBytes

- ea: `0x140223ab0`
- end: `0x14022404d`
- name: `NtfsWriteBytes`
- size: `1437`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID Buffer, int, int)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x1401509dc`
- `0x1401578f0`
- `0x14015f670`
- `0x1401700f0`
- `0x1402266e0`
- `0x14027e418`

## callees

- `0x1400055f0`
- `0x140007ea0`
- `0x14000c290`
- `0x140015b90`
- `0x140033250`
- `0x140037db4`
- `0x140059740`
- `0x140175ad0`
- `0x140223ab0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140223fdc`
- `ntoskrnl!IoFreeIrp` at `0x1402b5d7e`
- `ntoskrnl!IoFreeIrp` at `0x140223fdc`
- `ntoskrnl!IoFreeIrp` at `0x1402b5d7e`
- `ntoskrnl!MmUnmapLockedPages` at `0x140224022`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402b5da5`
- `ntoskrnl!MmUnmapLockedPages` at `0x140224022`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402b5da5`
- `ntoskrnl!IoAllocateMdl` at `0x140223c2c`
- `ntoskrnl!IoAllocateMdl` at `0x140223c2c`
- `ntoskrnl!MmProbeAndLockPages` at `0x140223c52`
- `ntoskrnl!MmProbeAndLockPages` at `0x140223c52`
- `ntoskrnl!IoFreeMdl` at `0x140223c65`
- `ntoskrnl!IoFreeMdl` at `0x140223d8d`
- `ntoskrnl!IoFreeMdl` at `0x14022400d`
- `ntoskrnl!IoFreeMdl` at `0x1402b5d6e`
- `ntoskrnl!IoFreeMdl` at `0x1402b5db5`
- `ntoskrnl!IoFreeMdl` at `0x1402cf17a`
- `ntoskrnl!IoFreeMdl` at `0x140223c65`
- `ntoskrnl!IoFreeMdl` at `0x140223d8d`
- `ntoskrnl!IoFreeMdl` at `0x14022400d`
- `ntoskrnl!IoFreeMdl` at `0x1402b5d6e`
- `ntoskrnl!IoFreeMdl` at `0x1402b5db5`
- `ntoskrnl!IoFreeMdl` at `0x1402cf17a`
- `ntoskrnl!MmMdlPageContentsState` at `0x140223ce0`
- `ntoskrnl!MmMdlPageContentsState` at `0x140223ce0`
- `ntoskrnl!MmUnlockPages` at `0x140223d78`
- `ntoskrnl!MmUnlockPages` at `0x14022403b`
- `ntoskrnl!MmUnlockPages` at `0x1402b5d5d`
- `ntoskrnl!MmUnlockPages` at `0x140223d78`
- `ntoskrnl!MmUnlockPages` at `0x14022403b`
- `ntoskrnl!MmUnlockPages` at `0x1402b5d5d`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140223ba8`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140223ba8`

## pseudocode

```c

```
