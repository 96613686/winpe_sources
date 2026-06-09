# CClfsManagedLog::UnlinkClient(CClfsManagedLogClient *)

- ea: `0x140051a9c`
- end: `0x140051b96`
- name: `?UnlinkClient@CClfsManagedLog@@QEAAJPEAVCClfsManagedLogClient@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(CClfsManagedLog *__hidden this, struct CClfsManagedLogClient *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14005d120`

## callees

- `0x140017f20`
- `0x140051a9c`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140051abd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140051abd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140051b34`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140051b34`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140051b70`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140051b70`
- `ntoskrnl!ExReleaseResourceLite` at `0x140051b60`
- `ntoskrnl!ExReleaseResourceLite` at `0x140051b60`

## pseudocode

```c

```
