# NlTransportDisableTransportName(ushort *)

- ea: `0x18005540c`
- end: `0x1800554c7`
- name: `?NlTransportDisableTransportName@@YAEPEAG@Z`
- size: `187`
- prototype: `unsigned __int8 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007070c`

## callees

- `0x180007278`
- `0x18005540c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005544b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005544b`
- `ntdll!NtClose` at `0x180055472`
- `ntdll!NtClose` at `0x180055472`
- `ntdll!RtlLeaveCriticalSection` at `0x180055487`
- `ntdll!RtlLeaveCriticalSection` at `0x1800554af`
- `ntdll!RtlLeaveCriticalSection` at `0x180055487`
- `ntdll!RtlLeaveCriticalSection` at `0x1800554af`
- `ntdll!RtlEnterCriticalSection` at `0x180055425`
- `ntdll!RtlEnterCriticalSection` at `0x180055425`

## string_xrefs

- `0x180055490`: `%ws: Transport Removed\n`

## pseudocode

```c

```
