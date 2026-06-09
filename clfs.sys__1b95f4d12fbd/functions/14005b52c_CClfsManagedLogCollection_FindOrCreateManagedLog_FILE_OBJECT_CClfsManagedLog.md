# CClfsManagedLogCollection::FindOrCreateManagedLog(_FILE_OBJECT *,CClfsManagedLog * *)

- ea: `0x14005b52c`
- end: `0x14005b619`
- name: `?FindOrCreateManagedLog@CClfsManagedLogCollection@@QEAAJPEAU_FILE_OBJECT@@PEAPEAVCClfsManagedLog@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(PUNICODE_PREFIX_TABLE PrefixTable, struct _FILE_OBJECT *, struct CClfsManagedLog **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14005bf20`

## callees

- `0x140017f20`
- `0x140059a48`
- `0x14005b52c`
- `0x14005b620`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005b566`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005b566`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b5bb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b5bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005b5e6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005b5e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b5d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b5d3`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14005b580`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14005b580`

## pseudocode

```c

```
