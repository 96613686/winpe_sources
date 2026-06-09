# FltOplockFsctrlEx

- ea: `0x180051d90`
- end: `0x180051ebf`
- name: `FltOplockFsctrlEx`
- size: `303`
- prototype: `FLT_PREOP_CALLBACK_STATUS __stdcall(POPLOCK Oplock, PFLT_CALLBACK_DATA CallbackData, ULONG OpenCount, ULONG Flags)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180051d70`
- `0x180085240`

## callees

- `0x180007230`
- `0x180009f20`
- `0x180051d90`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180051e24`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180051e24`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180051e4a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180051e4a`
- `ntoskrnl!FsRtlOplockFsctrlEx` at `0x180051e3c`
- `ntoskrnl!FsRtlOplockFsctrlEx` at `0x180051e3c`

## pseudocode

```c

```
