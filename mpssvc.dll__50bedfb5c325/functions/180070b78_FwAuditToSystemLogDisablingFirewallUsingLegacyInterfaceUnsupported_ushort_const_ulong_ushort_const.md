# FwAuditToSystemLogDisablingFirewallUsingLegacyInterfaceUnsupported(ushort const *,ulong,ushort const *)

- ea: `0x180070b78`
- end: `0x180070d62`
- name: `?FwAuditToSystemLogDisablingFirewallUsingLegacyInterfaceUnsupported@@YAJPEBGK0@Z`
- size: `490`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007e4f0`

## callees

- `0x18000a710`
- `0x180070b78`
- `0x1800729c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180070ca4`
- `ntdll!EtwEventWrite` at `0x180070ca4`
- `ntdll!EtwEventUnregister` at `0x180070d2e`
- `ntdll!EtwEventUnregister` at `0x180070d2e`
- `ntdll!EtwEventRegister` at `0x180070bcd`
- `ntdll!EtwEventRegister` at `0x180070bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070cc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070cc8`
- `fwbase!FwReportReturnError` at `0x180070d19`
- `fwbase!FwReportReturnError` at `0x180070d19`

## pseudocode

```c

```
