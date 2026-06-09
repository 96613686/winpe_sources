# RefsDeviceIoControlAsync2

- ea: `0x1c01a70a8`
- end: `0x1c01a7384`
- name: `RefsDeviceIoControlAsync2`
- size: `732`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, SIZE_T NumberOfBytes, char, int)`
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1c00697d0`
- `0x1c00977bc`
- `0x1c009ab20`
- `0x1c009af90`
- `0x1c009bc90`
- `0x1c009cc20`
- `0x1c01bfee0`

## callees

- `0x1c000f770`
- `0x1c000f920`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006acc0`
- `0x1c01a70a8`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01a719a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01a719a`
- `ntoskrnl!IofCompleteRequest` at `0x1c01a72f7`
- `ntoskrnl!IofCompleteRequest` at `0x1c01a72f7`
- `ntoskrnl!IoFreeIrp` at `0x1c01a71b2`
- `ntoskrnl!IoFreeIrp` at `0x1c01a71b2`
- `ntoskrnl!IoSetIoPriorityHint` at `0x1c01a72b5`
- `ntoskrnl!IoSetIoPriorityHint` at `0x1c01a72b5`
- `ntoskrnl!IoAllocateIrpEx` at `0x1c01a70eb`
- `ntoskrnl!IoAllocateIrpEx` at `0x1c01a70eb`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x1c01a729e`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x1c01a729e`

## pseudocode

```c

```
