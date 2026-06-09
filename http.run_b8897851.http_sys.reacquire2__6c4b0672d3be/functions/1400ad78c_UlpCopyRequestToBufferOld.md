# UlpCopyRequestToBufferOld

- ea: `0x1400ad78c`
- end: `0x1400aeaf3`
- name: `UlpCopyRequestToBufferOld`
- size: `4967`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PIRP Irp@<rdx>, int, int, char, char, char, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x14003c144`
- `0x1400406c0`

## callees

- `0x14000a350`
- `0x140022610`
- `0x1400518c0`
- `0x140065010`
- `0x1400ac030`
- `0x1400ad78c`
- `0x1400aeafc`
- `0x1400aec0c`
- `0x1401677e0`
- `0x140167840`
- `0x140167b40`
- `0x1401c37f8`
- `0x1401c49c4`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x1400aea78`
- `ntoskrnl!ObCloseHandle` at `0x1400aea94`
- `ntoskrnl!ObCloseHandle` at `0x1400aea78`
- `ntoskrnl!ObCloseHandle` at `0x1400aea94`
- `ntoskrnl!ExRaiseStatus` at `0x1400ae556`
- `ntoskrnl!ExRaiseStatus` at `0x1400ae556`
- `ntoskrnl!IoIs32bitProcess` at `0x1400ad7f0`
- `ntoskrnl!IoIs32bitProcess` at `0x1400ad7f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ae7fc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ae7fc`
- `ntoskrnl!ExAllocatePool3` at `0x1400ada33`
- `ntoskrnl!ExAllocatePool3` at `0x1400ada33`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aead1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aead1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ae7f0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ae7f0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ad7d5`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ad7d5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ae79f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ae79f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ae786`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ae786`
- `HAL!KeQueryPerformanceCounter` at `0x1400ae35e`
- `HAL!KeQueryPerformanceCounter` at `0x1400ae565`
- `HAL!KeQueryPerformanceCounter` at `0x1400ae35e`
- `HAL!KeQueryPerformanceCounter` at `0x1400ae565`

## pseudocode

```c

```
