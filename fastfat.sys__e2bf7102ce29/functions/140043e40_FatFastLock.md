# FatFastLock

- ea: `0x140043e40`
- end: `0x140043feb`
- name: `FatFastLock`
- size: `427`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PLARGE_INTEGER FileOffset, PLARGE_INTEGER Length, PEPROCESS ProcessId, ULONG, BOOLEAN, BOOLEAN, PIO_STATUS_BLOCK)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x14003d880`
- `0x140043e40`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140043eae`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140043eae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140043fd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f53a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140043fd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f53a`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140043edc`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140043f78`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140043edc`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140043f78`
- `ntoskrnl!FsRtlPrivateLock` at `0x140043f4b`
- `ntoskrnl!FsRtlPrivateLock` at `0x140043f4b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140043fcb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f52e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140043fcb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f52e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140043ecb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140043ecb`

## pseudocode

```c

```
