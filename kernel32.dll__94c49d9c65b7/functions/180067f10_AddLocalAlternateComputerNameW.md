# AddLocalAlternateComputerNameW

- ea: `0x180067f10`
- end: `0x18006802c`
- name: `AddLocalAlternateComputerNameW`
- size: `284`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180067eb0`

## callees

- `0x18003dfb0`
- `0x180067f10`
- `0x180068034`
- `0x180068820`
- `0x180079f94`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180067f60`
- `ntdll!RtlNtStatusToDosError` at `0x180067f60`
- `ntdll!RtlFreeHeap` at `0x18006800d`
- `ntdll!RtlFreeHeap` at `0x18006800d`
- `ntdll!RtlAllocateHeap` at `0x180067fbc`
- `ntdll!RtlAllocateHeap` at `0x180067fbc`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180067fa3`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180067fa3`

## string_xrefs

- `0x180067f52`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x180067f4b`: `AlternateComputerNames`

## pseudocode

```c

```
