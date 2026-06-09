# UlpCopyRequestToBuffer

- ea: `0x1400a6e84`
- end: `0x1400a7531`
- name: `UlpCopyRequestToBuffer`
- size: `1709`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PIRP Irp@<rdx>, __int64, int, char, char, int, char, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x14003c144`
- `0x1400406c0`

## callees

- `0x14000a350`
- `0x140022610`
- `0x1400a6e84`
- `0x140122db8`
- `0x14012310c`
- `0x14012393c`
- `0x140125434`
- `0x1401266d0`
- `0x140127618`
- `0x1401279b0`
- `0x140127fbc`
- `0x1401677e0`
- `0x1401c37f8`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x1400a74b4`
- `ntoskrnl!ObCloseHandle` at `0x1400a74cb`
- `ntoskrnl!ObCloseHandle` at `0x1400a74b4`
- `ntoskrnl!ObCloseHandle` at `0x1400a74cb`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a6ee1`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a6ee1`
- `ntoskrnl!ExAllocatePool3` at `0x1400a70dd`
- `ntoskrnl!ExAllocatePool3` at `0x1400a70dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7506`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7506`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a6ec3`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a6ec3`
- `HAL!KeQueryPerformanceCounter` at `0x1400a727d`
- `HAL!KeQueryPerformanceCounter` at `0x1400a729c`
- `HAL!KeQueryPerformanceCounter` at `0x1400a727d`
- `HAL!KeQueryPerformanceCounter` at `0x1400a729c`

## pseudocode

```c

```
