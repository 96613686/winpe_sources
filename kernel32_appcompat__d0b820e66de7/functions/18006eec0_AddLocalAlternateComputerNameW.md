# AddLocalAlternateComputerNameW

- ea: `0x18006eec0`
- end: `0x18006eff9`
- name: `AddLocalAlternateComputerNameW`
- size: `313`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006ee60`

## callees

- `0x180041720`
- `0x18006eec0`
- `0x18006f000`
- `0x18006f8ec`
- `0x180081e0c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18006ef10`
- `ntdll!RtlNtStatusToDosError` at `0x18006ef10`
- `ntdll!RtlFreeHeap` at `0x18006efd3`
- `ntdll!RtlFreeHeap` at `0x18006efd3`
- `ntdll!RtlAllocateHeap` at `0x18006ef7c`
- `ntdll!RtlAllocateHeap` at `0x18006ef7c`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006ef5d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006ef5d`

## string_xrefs

- `0x18006ef02`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x18006eefb`: `AlternateComputerNames`

## pseudocode

```c

```
