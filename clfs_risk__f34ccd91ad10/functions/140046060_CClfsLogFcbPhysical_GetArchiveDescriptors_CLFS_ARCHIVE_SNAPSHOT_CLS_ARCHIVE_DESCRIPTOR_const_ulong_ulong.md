# CClfsLogFcbPhysical::GetArchiveDescriptors(_CLFS_ARCHIVE_SNAPSHOT &,_CLS_ARCHIVE_DESCRIPTOR * const,ulong,ulong &)

- ea: `0x140046060`
- end: `0x1400465e5`
- name: `?GetArchiveDescriptors@CClfsLogFcbPhysical@@UEAAJAEAU_CLFS_ARCHIVE_SNAPSHOT@@QEAU_CLS_ARCHIVE_DESCRIPTOR@@KAEAK@Z`
- size: `1413`
- prototype: `__int64 __usercall@<rax>(ULONG_PTR BugCheckParameter2@<rcx>, CLFS_LSN *plsn@<rdx>, struct _CLS_ARCHIVE_DESCRIPTOR *const@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x140015600`

## callees

- `0x140003590`
- `0x140005840`
- `0x140005f00`
- `0x140007034`
- `0x14000a420`
- `0x140017f20`
- `0x140017f80`
- `0x140018280`
- `0x140038b18`
- `0x1400394e4`
- `0x14003ea10`
- `0x140046060`
- `0x140061c00`
- `0x140061d00`
- `0x140062980`
- `0x140062a30`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004616a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004616a`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140046495`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140046495`
- `ntoskrnl!KeBugCheckEx` at `0x14004619a`
- `ntoskrnl!KeBugCheckEx` at `0x14004619a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004614a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004614a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400465bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fc58`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400465bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fc58`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046264`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046264`

## pseudocode

```c

```
