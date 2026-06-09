# KerbRenewTicket(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,_KERB_EXTRA_CRED *,_KERB_PROXY_LOGON_CRED *,_KERB_TICKET_CACHE_ENTRY *,ulong,uchar,_KERB_TICKET_CACHE_ENTRY * *)

- ea: `0x180041ff0`
- end: `0x180042462`
- name: `?KerbRenewTicket@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAU_KERB_EXTRA_CRED@@PEAU_KERB_PROXY_LOGON_CRED@@PEAU_KERB_TICKET_CACHE_ENTRY@@KEPEAPEAU6@@Z`
- size: `1138`
- prototype: `__int64 __usercall@<rax>(struct _KERB_LOGON_SESSION *@<rcx>, struct _KERB_CREDENTIAL *@<rdx>, struct _KERB_CREDMAN_CRED *@<r8>, struct _KERB_EXTRA_CRED *@<r9>, struct _KERB_PROXY_LOGON_CRED *, PRTL_CRITICAL_SECTION CriticalSection, unsigned int, unsigned __int8, struct _KERB_TICKET_CACHE_ENTRY **)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180088264`

## callees

- `0x1800063e8`
- `0x1800068d0`
- `0x1800069e0`
- `0x18000b300`
- `0x1800113f0`
- `0x1800290c0`
- `0x180040fb8`
- `0x180041ff0`
- `0x18004ed20`
- `0x18006cd70`
- `0x18006d240`
- `0x18008a304`
- `0x18008b70c`
- `0x180093080`
- `0x1800c0374`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800423a5`
- `ntdll!RtlReleaseResource` at `0x1800423fb`
- `ntdll!RtlReleaseResource` at `0x1800423a5`
- `ntdll!RtlReleaseResource` at `0x1800423fb`
- `ntdll!RtlAcquireResourceShared` at `0x18004237f`
- `ntdll!RtlAcquireResourceShared` at `0x18004237f`
- `ntdll!RtlEnterCriticalSection` at `0x180042255`
- `ntdll!RtlEnterCriticalSection` at `0x180042255`
- `ntdll!RtlLeaveCriticalSection` at `0x18004240f`
- `ntdll!RtlLeaveCriticalSection` at `0x18004240f`

## string_xrefs

- `0x18004230a`: `KerbRenewTicket failed to create a ticket cache entry %#x\n`

## pseudocode

```c

```
