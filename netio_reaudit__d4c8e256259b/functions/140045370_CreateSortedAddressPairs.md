# CreateSortedAddressPairs

- ea: `0x140045370`
- end: `0x1400455f9`
- name: `CreateSortedAddressPairs`
- size: `649`
- prototype: `NTSTATUS __stdcall(const PSOCKADDR_IN6 SourceAddressList, ULONG SourceAddressCount, const PSOCKADDR_IN6 DestinationAddressList, ULONG DestinationAddressCount, ULONG AddressSortOptions, PSOCKADDR_IN6_PAIR *SortedAddressPairList, ULONG *SortedAddressPairCount)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140023090`
- `0x1400244e0`
- `0x140045370`
- `0x140078100`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400453e6`
- `ntoskrnl!ExAllocatePool2` at `0x1400453ff`
- `ntoskrnl!ExAllocatePool2` at `0x140045501`
- `ntoskrnl!ExAllocatePool2` at `0x1400453e6`
- `ntoskrnl!ExAllocatePool2` at `0x1400453ff`
- `ntoskrnl!ExAllocatePool2` at `0x140045501`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400455bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400455d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400455bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400455d4`

## pseudocode

```c

```
