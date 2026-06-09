# NtfsPagingFileIoWithNoAllocation

- ea: `0x1400133cc`
- end: `0x140013ba9`
- name: `NtfsPagingFileIoWithNoAllocation`
- size: `2013`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, SIZE_T NumberOfBytes)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x140013bb0`

## callees

- `0x14000549c`
- `0x140005558`
- `0x140007670`
- `0x140007ea0`
- `0x1400082b0`
- `0x14001310c`
- `0x1400133cc`
- `0x140014e74`
- `0x1400247a4`
- `0x14003c2f0`
- `0x1400463dc`
- `0x140059250`
- `0x140059370`
- `0x1400596c0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140013a7e`
- `ntoskrnl!KeBugCheckEx` at `0x140013a7e`
- `ntoskrnl!IoBuildPartialMdl` at `0x140013700`
- `ntoskrnl!IoBuildPartialMdl` at `0x140013700`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400136d8`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400136d8`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x14001383a`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x14001383a`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400138c2`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140013906`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400138c2`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140013906`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013867`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013867`
- `ntoskrnl!KeInitializeEvent` at `0x140013494`
- `ntoskrnl!KeInitializeEvent` at `0x140013494`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14001389b`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14001389b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b72`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400134f1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400134f1`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140013604`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140013604`

## pseudocode

```c

```
