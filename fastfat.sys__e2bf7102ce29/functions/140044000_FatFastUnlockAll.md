# FatFastUnlockAll

- ea: `0x140044000`
- end: `0x14004415b`
- name: `FatFastUnlockAll`
- size: `347`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PEPROCESS ProcessId)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x14003d880`
- `0x140044000`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140044070`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140044070`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044147`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f571`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044147`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f571`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x1400440c6`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x1400440c6`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14004409e`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400440eb`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14004409e`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400440eb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004413b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f565`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004413b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f565`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004408d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004408d`

## pseudocode

```c

```
