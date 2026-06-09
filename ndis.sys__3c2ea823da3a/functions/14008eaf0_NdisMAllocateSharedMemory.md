# NdisMAllocateSharedMemory

- ea: `0x14008eaf0`
- end: `0x14008ee9b`
- name: `NdisMAllocateSharedMemory`
- size: `939`
- prototype: `void __stdcall(NDIS_HANDLE MiniportAdapterHandle, ULONG Length, BOOLEAN Cached, PVOID *VirtualAddress, PNDIS_PHYSICAL_ADDRESS PhysicalAddress)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14008da80`

## callees

- `0x14001d350`
- `0x140028b60`
- `0x140029b00`
- `0x1400837ac`
- `0x14008eaf0`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14008ebe9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14008ebe9`
- `ntoskrnl!DbgPrintEx` at `0x14008ec1e`
- `ntoskrnl!DbgPrintEx` at `0x14008edfd`
- `ntoskrnl!DbgPrintEx` at `0x14008ec1e`
- `ntoskrnl!DbgPrintEx` at `0x14008edfd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008ed97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008ed97`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008ec75`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008ec75`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14008ec8a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14008ec8a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008ed39`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008ed39`
- `ntoskrnl!KeBugCheckEx` at `0x14008ec3d`
- `ntoskrnl!KeBugCheckEx` at `0x14008ee1c`
- `ntoskrnl!KeBugCheckEx` at `0x14008ec3d`
- `ntoskrnl!KeBugCheckEx` at `0x14008ee1c`
- `HAL!KeQueryPerformanceCounter` at `0x14008eb66`
- `HAL!KeQueryPerformanceCounter` at `0x14008eb66`

## pseudocode

```c

```
