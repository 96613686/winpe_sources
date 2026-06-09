# RefsBreakBatchOplock

- ea: `0x1403099e0`
- end: `0x140309ca5`
- name: `RefsBreakBatchOplock`
- size: `709`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, PIRP Irp@<rdx>, __int64, __int16, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1403096d0`
- `0x140332e30`

## callees

- `0x140076ad0`
- `0x1400862c0`
- `0x14008ec60`
- `0x1400d0fd8`
- `0x1403099e0`
- `0x140309cb0`

## import_xrefs

- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x140309bb9`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x14034c2e3`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x14034c43a`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x140309bb9`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x14034c2e3`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x14034c43a`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x14034c38d`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x14034c496`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x14034c38d`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x14034c496`
- `ntoskrnl!FsRtlOplockBreakH` at `0x14034c3c6`
- `ntoskrnl!FsRtlOplockBreakH` at `0x14034c4cf`
- `ntoskrnl!FsRtlOplockBreakH` at `0x14034c3c6`
- `ntoskrnl!FsRtlOplockBreakH` at `0x14034c4cf`
- `ntoskrnl!FsRtlCheckOplock` at `0x14034c31d`
- `ntoskrnl!FsRtlCheckOplock` at `0x14034c470`
- `ntoskrnl!FsRtlCheckOplock` at `0x14034c772`
- `ntoskrnl!FsRtlCheckOplock` at `0x14034c31d`
- `ntoskrnl!FsRtlCheckOplock` at `0x14034c470`
- `ntoskrnl!FsRtlCheckOplock` at `0x14034c772`

## string_xrefs

- `0x140309ae8`: `Create.c`
- `0x14034c5b5`: `Create.c`
- `0x14034c6a2`: `Create.c`
- `0x14034c727`: `Create.c`
- `0x14034c7d5`: `Create.c`

## pseudocode

```c

```
