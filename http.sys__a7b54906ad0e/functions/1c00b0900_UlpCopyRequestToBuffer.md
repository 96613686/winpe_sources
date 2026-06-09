# UlpCopyRequestToBuffer

- ea: `0x1c00b0900`
- end: `0x1c00b1c99`
- name: `UlpCopyRequestToBuffer`
- size: `5017`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PIRP Irp@<rdx>, int, int, int, char, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1c00b0480`
- `0x1c00b2b20`

## callees

- `0x1c0001ae0`
- `0x1c001a548`
- `0x1c001a8ac`
- `0x1c001b610`
- `0x1c001b640`
- `0x1c001b900`
- `0x1c0047228`
- `0x1c008f374`
- `0x1c008f4f0`
- `0x1c00b0900`
- `0x1c00b1ca0`
- `0x1c0128fa4`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x1c00e5fc0`
- `ntoskrnl!ObCloseHandle` at `0x1c00e5fdf`
- `ntoskrnl!ObCloseHandle` at `0x1c00e5fc0`
- `ntoskrnl!ObCloseHandle` at `0x1c00e5fdf`
- `ntoskrnl!ExRaiseStatus` at `0x1c00b19a9`
- `ntoskrnl!ExRaiseStatus` at `0x1c00b19a9`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b0964`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b0964`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00e5ed5`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00e5ed5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00e5ff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00e5ff6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00b1aa1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00b1aa1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00b1a59`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00b1a59`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00b1aad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00b1aad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00b1a40`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00b1a40`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00b0945`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00b0945`
- `HAL!KeQueryPerformanceCounter` at `0x1c00b1114`
- `HAL!KeQueryPerformanceCounter` at `0x1c00b19b6`
- `HAL!KeQueryPerformanceCounter` at `0x1c00b1114`
- `HAL!KeQueryPerformanceCounter` at `0x1c00b19b6`

## pseudocode

```c

```
