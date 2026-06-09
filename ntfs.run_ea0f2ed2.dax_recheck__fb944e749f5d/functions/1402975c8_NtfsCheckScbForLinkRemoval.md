# NtfsCheckScbForLinkRemoval

- ea: `0x1402975c8`
- end: `0x140297d1a`
- name: `NtfsCheckScbForLinkRemoval`
- size: `1874`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, CLFS_LSN *plsn2)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1402472e8`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x140012e70`
- `0x140031a50`
- `0x14003f358`
- `0x14003f52c`
- `0x1400ff9cc`
- `0x14018dc4c`
- `0x1401dc5e8`
- `0x14022c80c`
- `0x1402975c8`

## import_xrefs

- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x14029786d`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x14029786d`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x140297881`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x140297881`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140297683`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140297683`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14029763a`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14029763a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140297a77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140297a77`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402978ed`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140297a2d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402978ed`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140297a2d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402979e1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140297a99`
- `ntoskrnl!ExReleaseResourceLite` at `0x140297cd1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402979e1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140297a99`
- `ntoskrnl!ExReleaseResourceLite` at `0x140297cd1`
- `ntoskrnl!ExAcquireFastMutex` at `0x140297764`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402979a8`
- `ntoskrnl!ExAcquireFastMutex` at `0x140297764`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402979a8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402977cd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402979ce`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402977cd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402979ce`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140297906`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140297906`
- `ntoskrnl!ExRaiseStatus` at `0x140297c9f`
- `ntoskrnl!ExRaiseStatus` at `0x140297c9f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14029796d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14029796d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140297a46`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140297a46`

## pseudocode

```c

```
