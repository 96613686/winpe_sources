# CmsVolumeContainer::Initialize(CmsTransactionContext *,_MS_CREATE_DISPOSITION,LcnWithChecksum * * const,ulong,_SmsVolumeContainerKsrContext *)

- ea: `0x14001e410`
- end: `0x14001eea2`
- name: `?Initialize@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@W4_MS_CREATE_DISPOSITION@@QEAPEAULcnWithChecksum@@KPEAU_SmsVolumeContainerKsrContext@@@Z`
- size: `2706`
- prototype: `int __high(struct CmsTransactionContext *, enum _MS_CREATE_DISPOSITION, struct LcnWithChecksum **const, unsigned int, struct _SmsVolumeContainerKsrContext *)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x1400ccae0`

## callees

- `0x14001ddec`
- `0x14001e410`
- `0x14001eea8`
- `0x140020310`
- `0x140032b20`
- `0x140034ab0`
- `0x140036df0`
- `0x140052070`
- `0x14005a160`
- `0x1400959c0`
- `0x14009c9d0`
- `0x1400c8d68`
- `0x14011cd28`
- `0x140136c24`
- `0x1401e9ce0`
- `0x1401e9dc0`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1401ef25f`
- `ntoskrnl!DbgPrintEx` at `0x1401ef2c8`
- `ntoskrnl!DbgPrintEx` at `0x1401ef25f`
- `ntoskrnl!DbgPrintEx` at `0x1401ef2c8`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001ed06`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001ed1c`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001ed32`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001ed8b`
- `ntoskrnl!ExAllocatePool2` at `0x14001e4c3`
- `ntoskrnl!ExAllocatePool2` at `0x14001e547`
- `ntoskrnl!ExAllocatePool2` at `0x14001e5f2`
- `ntoskrnl!ExAllocatePool2` at `0x14001eb2b`
- `ntoskrnl!ExAllocatePool2` at `0x1401ef186`
- `ntoskrnl!ExAllocatePool2` at `0x14001e4c3`
- `ntoskrnl!ExAllocatePool2` at `0x14001e547`
- `ntoskrnl!ExAllocatePool2` at `0x14001e5f2`
- `ntoskrnl!ExAllocatePool2` at `0x14001eb2b`
- `ntoskrnl!ExAllocatePool2` at `0x1401ef186`
- `ntoskrnl!RtlCreateHashTableEx` at `0x14001e503`
- `ntoskrnl!RtlCreateHashTableEx` at `0x14001e503`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001eb83`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001eb83`
- `HAL!KeQueryPerformanceCounter` at `0x14001ee10`
- `HAL!KeQueryPerformanceCounter` at `0x1401ef22f`
- `HAL!KeQueryPerformanceCounter` at `0x1401ef289`
- `HAL!KeQueryPerformanceCounter` at `0x14001ee10`
- `HAL!KeQueryPerformanceCounter` at `0x1401ef22f`
- `HAL!KeQueryPerformanceCounter` at `0x1401ef289`

## pseudocode

```c

```
