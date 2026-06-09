# KerbGetKdcBinding_Old(_UNICODE_STRING *,_UNICODE_STRING *,ulong,uchar,uchar,_KERB_BINDING_CACHE_ENTRY * *)

- ea: `0x1800389b8`
- end: `0x180039417`
- name: `?KerbGetKdcBinding_Old@@YAJPEAU_UNICODE_STRING@@0KEEPEAPEAU_KERB_BINDING_CACHE_ENTRY@@@Z`
- size: `2655`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1, PCUNICODE_STRING String2, unsigned int, unsigned __int8, unsigned __int8, struct _KERB_BINDING_CACHE_ENTRY **)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180037e30`

## callees

- `0x1800068d0`
- `0x180007e80`
- `0x18000b300`
- `0x18003003c`
- `0x1800389b8`
- `0x18004fcb0`
- `0x180050f70`
- `0x180051450`
- `0x18005ebb0`
- `0x18005edf8`
- `0x180065fa4`
- `0x18006ba6c`
- `0x18006cb94`
- `0x18006cc70`
- `0x180070680`
- `0x1800744cf`
- `0x1800783b0`
- `0x180078fa4`
- `0x180079338`
- `0x18008b70c`
- `0x180091754`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180038a64`
- `ntdll!RtlEqualUnicodeString` at `0x180038a64`
- `ntdll!RtlEqualDomainName` at `0x180038ac6`
- `ntdll!RtlEqualDomainName` at `0x180038ac6`
- `ntdll!RtlInitUnicodeString` at `0x18003930f`
- `ntdll!RtlInitUnicodeString` at `0x180039324`
- `ntdll!RtlInitUnicodeString` at `0x18003930f`
- `ntdll!RtlInitUnicodeString` at `0x180039324`
- `ntdll!RtlReleaseResource` at `0x180038a83`
- `ntdll!RtlReleaseResource` at `0x180038e72`
- `ntdll!RtlReleaseResource` at `0x180038a83`
- `ntdll!RtlReleaseResource` at `0x180038e72`
- `ntdll!RtlAcquireResourceShared` at `0x180038a44`
- `ntdll!RtlAcquireResourceShared` at `0x180038a44`
- `ntdll!RtlAcquireResourceExclusive` at `0x180038e4e`
- `ntdll!RtlAcquireResourceExclusive` at `0x180038e4e`
- `ntdll!RtlEnterCriticalSection` at `0x180038c7a`
- `ntdll!RtlEnterCriticalSection` at `0x180038c7a`
- `ntdll!RtlLeaveCriticalSection` at `0x180038d31`
- `ntdll!RtlLeaveCriticalSection` at `0x180038d45`
- `ntdll!RtlLeaveCriticalSection` at `0x180038d9b`
- `ntdll!RtlLeaveCriticalSection` at `0x180038de1`
- `ntdll!RtlLeaveCriticalSection` at `0x180038d31`
- `ntdll!RtlLeaveCriticalSection` at `0x180038d45`
- `ntdll!RtlLeaveCriticalSection` at `0x180038d9b`
- `ntdll!RtlLeaveCriticalSection` at `0x180038de1`
- `NETLOGON!DsrGetDcNameEx2` at `0x1800390be`
- `NETLOGON!DsrGetDcNameEx2` at `0x1800390be`
- `NETLOGON!I_NetLogonFree` at `0x1800393db`
- `NETLOGON!I_NetLogonFree` at `0x1800393db`
- `logoncli!DsGetDcNameW` at `0x1800391c7`
- `logoncli!DsGetDcNameW` at `0x1800391c7`
- `netutils!NetApiBufferFree` at `0x1800393e3`
- `netutils!NetApiBufferFree` at `0x1800393e3`

## string_xrefs

- `0x180038ae1`: `Attempting to locate a KDC for the workstation - failing\n`
- `0x180038e80`: `KerbIsTcpNotInstalled failed 0x%x\n`
- `0x180039066`: `\NETLOGON_SERVICE_STARTED`

## pseudocode

```c

```
