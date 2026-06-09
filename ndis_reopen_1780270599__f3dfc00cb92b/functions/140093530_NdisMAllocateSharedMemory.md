# NdisMAllocateSharedMemory

- ea: `0x140093530`
- end: `0x1400938db`
- name: `NdisMAllocateSharedMemory`
- size: `939`
- prototype: `void __stdcall(NDIS_HANDLE MiniportAdapterHandle, ULONG Length, BOOLEAN Cached, PVOID *VirtualAddress, PNDIS_PHYSICAL_ADDRESS PhysicalAddress)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400924c0`

## callees

- `0x1400114b0`
- `0x14001ccc0`
- `0x14001dbb0`
- `0x140088a2c`
- `0x140093530`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140093629`
- `ntoskrnl!KeGetCurrentIrql` at `0x140093629`
- `ntoskrnl!DbgPrintEx` at `0x14009365e`
- `ntoskrnl!DbgPrintEx` at `0x14009383d`
- `ntoskrnl!DbgPrintEx` at `0x14009365e`
- `ntoskrnl!DbgPrintEx` at `0x14009383d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400937d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400937d7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400936b5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400936b5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400936ca`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400936ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x140093779`
- `ntoskrnl!ExReleaseResourceLite` at `0x140093779`
- `ntoskrnl!KeBugCheckEx` at `0x14009367d`
- `ntoskrnl!KeBugCheckEx` at `0x14009385c`
- `ntoskrnl!KeBugCheckEx` at `0x14009367d`
- `ntoskrnl!KeBugCheckEx` at `0x14009385c`
- `HAL!KeQueryPerformanceCounter` at `0x1400935a6`
- `HAL!KeQueryPerformanceCounter` at `0x1400935a6`

## pseudocode

```c

```
