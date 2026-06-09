# FltGetFileNameInformation

- ea: `0x18000dff0`
- end: `0x18000e2ce`
- name: `FltGetFileNameInformation`
- size: `734`
- prototype: `NTSTATUS __stdcall(PFLT_CALLBACK_DATA CallbackData, FLT_FILE_NAME_OPTIONS NameOptions, PFLT_FILE_NAME_INFORMATION *FileNameInformation)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180022dac`
- `0x1800763a0`
- `0x18007ea20`

## callees

- `0x180009f20`
- `0x18000dcb0`
- `0x18000dff0`
- `0x18000e2e0`
- `0x18000eb80`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x18000e080`
- `ntoskrnl!IoGetTopLevelIrp` at `0x18000e2ab`
- `ntoskrnl!IoGetTopLevelIrp` at `0x18000e080`
- `ntoskrnl!IoGetTopLevelIrp` at `0x18000e2ab`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x18000e23f`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x18000e23f`

## string_xrefs

- `0x18000e0d4`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x18000e17b`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x18000e1a7`: `minkernel\fs\filtermgr\filter\namecachesup.c`

## pseudocode

```c

```
