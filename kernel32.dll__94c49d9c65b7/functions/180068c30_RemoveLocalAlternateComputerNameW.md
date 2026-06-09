# RemoveLocalAlternateComputerNameW

- ea: `0x180068c30`
- end: `0x180068d64`
- name: `RemoveLocalAlternateComputerNameW`
- size: `308`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004ed70`
- `0x180068bd0`

## callees

- `0x18000f920`
- `0x18003dfb0`
- `0x180068330`
- `0x1800685dc`
- `0x180068c30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180068c73`
- `ntdll!RtlNtStatusToDosError` at `0x180068c73`
- `ntdll!RtlFreeHeap` at `0x180068d45`
- `ntdll!RtlFreeHeap` at `0x180068d45`
- `ntdll!RtlAllocateHeap` at `0x180068cd3`
- `ntdll!RtlAllocateHeap` at `0x180068cd3`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180068cba`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180068cba`

## string_xrefs

- `0x180068c65`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x180068c5e`: `AlternateComputerNames`
- `0x180068d10`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c

```
