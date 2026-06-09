# NlTransportDisableTransportName(ushort *)

- ea: `0x180059060`
- end: `0x18005913a`
- name: `?NlTransportDisableTransportName@@YAEPEAG@Z`
- size: `218`
- prototype: `unsigned __int8 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180075b60`

## callees

- `0x180007518`
- `0x180059060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800590a5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800590a5`
- `ntdll!NtClose` at `0x1800590d2`
- `ntdll!NtClose` at `0x1800590d2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800590ed`
- `ntdll!RtlLeaveCriticalSection` at `0x18005911b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800590ed`
- `ntdll!RtlLeaveCriticalSection` at `0x18005911b`
- `ntdll!RtlEnterCriticalSection` at `0x180059079`
- `ntdll!RtlEnterCriticalSection` at `0x180059079`

## string_xrefs

- `0x1800590fc`: `%ws: Transport Removed\n`

## pseudocode

```c

```
