# RefsBreakBatchOplock

- ea: `0x140306360`
- end: `0x140306625`
- name: `RefsBreakBatchOplock`
- size: `709`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, PIRP Irp@<rdx>, __int64, __int16, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140306050`
- `0x140331170`

## callees

- `0x140081670`
- `0x14008dbd0`
- `0x140094fc0`
- `0x1400ca788`
- `0x140306360`
- `0x140306630`

## import_xrefs

- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x140306539`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x140349357`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x1403494ae`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x140306539`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x140349357`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x1403494ae`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x140349401`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x14034950a`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x140349401`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x14034950a`
- `ntoskrnl!FsRtlOplockBreakH` at `0x14034943a`
- `ntoskrnl!FsRtlOplockBreakH` at `0x140349543`
- `ntoskrnl!FsRtlOplockBreakH` at `0x14034943a`
- `ntoskrnl!FsRtlOplockBreakH` at `0x140349543`
- `ntoskrnl!FsRtlCheckOplock` at `0x140349391`
- `ntoskrnl!FsRtlCheckOplock` at `0x1403494e4`
- `ntoskrnl!FsRtlCheckOplock` at `0x1403497e6`
- `ntoskrnl!FsRtlCheckOplock` at `0x140349391`
- `ntoskrnl!FsRtlCheckOplock` at `0x1403494e4`
- `ntoskrnl!FsRtlCheckOplock` at `0x1403497e6`

## string_xrefs

- `0x140306468`: `Create.c`
- `0x140349629`: `Create.c`
- `0x140349716`: `Create.c`
- `0x14034979b`: `Create.c`
- `0x140349849`: `Create.c`

## pseudocode

```c

```
