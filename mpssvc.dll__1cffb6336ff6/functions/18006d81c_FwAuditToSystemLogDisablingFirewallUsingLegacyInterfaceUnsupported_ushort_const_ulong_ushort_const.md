# FwAuditToSystemLogDisablingFirewallUsingLegacyInterfaceUnsupported(ushort const *,ulong,ushort const *)

- ea: `0x18006d81c`
- end: `0x18006d9e1`
- name: `?FwAuditToSystemLogDisablingFirewallUsingLegacyInterfaceUnsupported@@YAJPEBGK0@Z`
- size: `453`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007a720`

## callees

- `0x18000af3c`
- `0x18006d81c`
- `0x18006f520`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18006d93c`
- `ntdll!EtwEventWrite` at `0x18006d93c`
- `ntdll!EtwEventUnregister` at `0x18006d9b4`
- `ntdll!EtwEventUnregister` at `0x18006d9b4`
- `ntdll!EtwEventRegister` at `0x18006d871`
- `ntdll!EtwEventRegister` at `0x18006d871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d89c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d95a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d89c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d95a`
- `fwbase!FwReportReturnError` at `0x18006d9a5`
- `fwbase!FwReportReturnError` at `0x18006d9a5`

## pseudocode

```c

```
