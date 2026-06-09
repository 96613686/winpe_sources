# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::SetFilePasteInformation(PPID const &,PPID const &,std::vector<Dlp::DragAndDrop::FileDescriptorInfo,std::allocator<Dlp::DragAndDrop::FileDescriptorInfo>> const &,bool)

- ea: `0x1801e6d28`
- end: `0x1801e6f5f`
- name: `?SetFilePasteInformation@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAXAEBUPPID@@0AEBV?$vector@UFileDescriptorInfo@DragAndDrop@Dlp@@V?$allocator@UFileDescriptorInfo@DragAndDrop@Dlp@@@std@@@std@@_N@Z`
- size: `567`
- prototype: `void __fastcall(__int64, __int64, struct _FILETIME *, Dlp::DragAndDrop::FileDescriptorInfo **, char)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1801d83f0`

## callees

- `0x18001bad0`
- `0x180024ac0`
- `0x1800809d0`
- `0x180094e70`
- `0x1800b7ed0`
- `0x18010cb40`
- `0x180185338`
- `0x1801dfe8c`
- `0x1801dff38`
- `0x1801e6d28`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1801e6de1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1801e6e02`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1801e6ef9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1801e6de1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1801e6e02`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1801e6ef9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801e6e7e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801e6e7e`

## pseudocode

```c

```
