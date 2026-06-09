# KerbGetKdcBindingEx(_UNICODE_STRING *,_UNICODE_STRING *,ulong,uchar,uchar,ulong,_KERB_BINDING_CACHE_ENTRY * *)

- ea: `0x180037ea8`
- end: `0x1800389b1`
- name: `?KerbGetKdcBindingEx@@YAJPEAU_UNICODE_STRING@@0KEEKPEAPEAU_KERB_BINDING_CACHE_ENTRY@@@Z`
- size: `2825`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING String1@<rcx>, PCUNICODE_STRING String2@<rdx>, unsigned int@<r8d>, unsigned __int8@<r9b>, unsigned __int8, unsigned int, struct _KERB_BINDING_CACHE_ENTRY **)`
- caller_count: `2`
- callee_count: `25`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180037e30`
- `0x1800670f8`

## callees

- `0x1800068d0`
- `0x180007e80`
- `0x18000b300`
- `0x18003003c`
- `0x180037ea8`
- `0x18004fcb0`
- `0x180050f70`
- `0x180051450`
- `0x18005ebb0`
- `0x18005edf8`
- `0x180065fa4`
- `0x18006ba20`
- `0x18006ba6c`
- `0x18006cb94`
- `0x18006cbb8`
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

- `ntdll!RtlEqualUnicodeString` at `0x180037f5c`
- `ntdll!RtlEqualUnicodeString` at `0x180037f5c`
- `ntdll!RtlEqualDomainName` at `0x180037fbe`
- `ntdll!RtlEqualDomainName` at `0x1800387df`
- `ntdll!RtlEqualDomainName` at `0x180037fbe`
- `ntdll!RtlEqualDomainName` at `0x1800387df`
- `ntdll!RtlInitUnicodeString` at `0x1800388a5`
- `ntdll!RtlInitUnicodeString` at `0x1800388ba`
- `ntdll!RtlInitUnicodeString` at `0x1800388a5`
- `ntdll!RtlInitUnicodeString` at `0x1800388ba`
- `ntdll!RtlReleaseResource` at `0x180037f7b`
- `ntdll!RtlReleaseResource` at `0x1800383ec`
- `ntdll!RtlReleaseResource` at `0x180037f7b`
- `ntdll!RtlReleaseResource` at `0x1800383ec`
- `ntdll!RtlAcquireResourceShared` at `0x180037f3b`
- `ntdll!RtlAcquireResourceShared` at `0x180037f3b`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800383c8`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800383c8`
- `ntdll!RtlEnterCriticalSection` at `0x18003815d`
- `ntdll!RtlEnterCriticalSection` at `0x18003815d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800382a3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800382b7`
- `ntdll!RtlLeaveCriticalSection` at `0x180038310`
- `ntdll!RtlLeaveCriticalSection` at `0x18003835e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800382a3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800382b7`
- `ntdll!RtlLeaveCriticalSection` at `0x180038310`
- `ntdll!RtlLeaveCriticalSection` at `0x18003835e`
- `NETLOGON!DsrGetDcNameEx2` at `0x18003863a`
- `NETLOGON!DsrGetDcNameEx2` at `0x18003863a`
- `NETLOGON!I_NetLogonFree` at `0x180038975`
- `NETLOGON!I_NetLogonFree` at `0x180038975`
- `logoncli!DsGetDcNameW` at `0x18003874f`
- `logoncli!DsGetDcNameW` at `0x18003874f`
- `netutils!NetApiBufferFree` at `0x18003897d`
- `netutils!NetApiBufferFree` at `0x18003897d`

## string_xrefs

- `0x180037fd8`: `Attempting to locate a KDC for the workstation - failing\n`
- `0x1800383fa`: `KerbIsTcpNotInstalled failed 0x%x\n`
- `0x1800385e3`: `\NETLOGON_SERVICE_STARTED`

## pseudocode

```c

```
