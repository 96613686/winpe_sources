# RemoveLocalAlternateComputerNameW

- ea: `0x18006fd70`
- end: `0x18006febd`
- name: `RemoveLocalAlternateComputerNameW`
- size: `333`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180053cc0`
- `0x18006fd10`

## callees

- `0x18000ccf0`
- `0x180041720`
- `0x18006f378`
- `0x18006f684`
- `0x18006fd70`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18006fdb3`
- `ntdll!RtlNtStatusToDosError` at `0x18006fdb3`
- `ntdll!RtlFreeHeap` at `0x18006fe97`
- `ntdll!RtlFreeHeap` at `0x18006fe97`
- `ntdll!RtlAllocateHeap` at `0x18006fe1f`
- `ntdll!RtlAllocateHeap` at `0x18006fe1f`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006fe00`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006fe00`

## string_xrefs

- `0x18006fda5`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x18006fd9e`: `AlternateComputerNames`
- `0x18006fe62`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c

```
