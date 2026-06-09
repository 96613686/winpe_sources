# RefsBreakBatchOplock

- ea: `0x1c0154578`
- end: `0x1c0154d54`
- name: `RefsBreakBatchOplock`
- size: `2012`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, PIRP Irp@<rdx>, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1c01540e0`
- `0x1c0194f50`

## callees

- `0x1c0002ce0`
- `0x1c0002ef8`
- `0x1c000f770`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0154578`
- `0x1c0156b80`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x1c01546f9`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c01548bf`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c0154aa5`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c01546f9`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c01548bf`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c0154aa5`
- `ntoskrnl!FsRtlOplockBreakH` at `0x1c01547a6`
- `ntoskrnl!FsRtlOplockBreakH` at `0x1c0154911`
- `ntoskrnl!FsRtlOplockBreakH` at `0x1c01547a6`
- `ntoskrnl!FsRtlOplockBreakH` at `0x1c0154911`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x1c01546c0`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x1c015488b`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x1c0154a50`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x1c01546c0`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x1c015488b`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x1c0154a50`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x1c015476a`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x1c01548dd`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x1c015476a`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x1c01548dd`

## string_xrefs

- `0x1c0154b73`: `Create.c`
- `0x1c0154beb`: `Create.c`
- `0x1c0154cd3`: `Create.c`
- `0x1c0154d3b`: `Create.c`

## pseudocode

```c

```
