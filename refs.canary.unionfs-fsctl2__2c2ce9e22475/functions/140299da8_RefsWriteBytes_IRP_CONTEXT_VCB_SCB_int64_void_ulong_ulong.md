# RefsWriteBytes(_IRP_CONTEXT *,_VCB *,_SCB *,__int64,void *,ulong,ulong)

- ea: `0x140299da8`
- end: `0x14029a51a`
- name: `?RefsWriteBytes@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAU_SCB@@_JPEAXKK@Z`
- size: `1906`
- prototype: `void __usercall(struct _IRP_CONTEXT *@<rcx>, struct _VCB *@<rdx>, struct _SCB *@<r8>, __int64@<r9>, void *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x14000b324`
- `0x1400ee9f8`

## callees

- `0x140081670`
- `0x14008dbd0`
- `0x14008f8b0`
- `0x1400ac034`
- `0x1400ca788`
- `0x1400cd71c`
- `0x1400e3e88`
- `0x1400ef6ac`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x140299da8`
- `0x14033b8d0`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x14029a4c8`
- `ntoskrnl!MmUnmapLockedPages` at `0x140343d95`
- `ntoskrnl!MmUnmapLockedPages` at `0x14029a4c8`
- `ntoskrnl!MmUnmapLockedPages` at `0x140343d95`
- `ntoskrnl!IoAllocateMdl` at `0x14029a104`
- `ntoskrnl!IoAllocateMdl` at `0x14029a104`
- `ntoskrnl!MmProbeAndLockPages` at `0x14029a1b6`
- `ntoskrnl!MmProbeAndLockPages` at `0x14029a1b6`
- `ntoskrnl!IoFreeMdl` at `0x14029a1df`
- `ntoskrnl!IoFreeMdl` at `0x14029a42f`
- `ntoskrnl!IoFreeMdl` at `0x14029a490`
- `ntoskrnl!IoFreeMdl` at `0x14029a4d7`
- `ntoskrnl!IoFreeMdl` at `0x140343d57`
- `ntoskrnl!IoFreeMdl` at `0x140343da5`
- `ntoskrnl!IoFreeMdl` at `0x14029a1df`
- `ntoskrnl!IoFreeMdl` at `0x14029a42f`
- `ntoskrnl!IoFreeMdl` at `0x14029a490`
- `ntoskrnl!IoFreeMdl` at `0x14029a4d7`
- `ntoskrnl!IoFreeMdl` at `0x140343d57`
- `ntoskrnl!IoFreeMdl` at `0x140343da5`
- `ntoskrnl!MmUnlockPages` at `0x14029a417`
- `ntoskrnl!MmUnlockPages` at `0x14029a480`
- `ntoskrnl!MmUnlockPages` at `0x140343d46`
- `ntoskrnl!MmUnlockPages` at `0x14029a417`
- `ntoskrnl!MmUnlockPages` at `0x14029a480`
- `ntoskrnl!MmUnlockPages` at `0x140343d46`
- `ntoskrnl!MmMdlPageContentsState` at `0x14029a0a5`
- `ntoskrnl!MmMdlPageContentsState` at `0x14029a0a5`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140299f6b`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140299f6b`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14029a20f`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14029a24f`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14029a27e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14029a20f`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14029a24f`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14029a27e`

## pseudocode

```c

```
