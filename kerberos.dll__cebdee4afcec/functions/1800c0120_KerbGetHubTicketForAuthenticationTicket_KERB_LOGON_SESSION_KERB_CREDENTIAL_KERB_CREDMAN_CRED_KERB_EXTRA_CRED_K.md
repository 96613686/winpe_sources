# KerbGetHubTicketForAuthenticationTicket(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,_KERB_EXTRA_CRED *,_KERB_PROXY_LOGON_CRED *,_UNICODE_STRING *,_KERB_TICKET_CACHE_ENTRY *,ulong,_KERB_TICKET_CACHE_ENTRY * *)

- ea: `0x1800c0120`
- end: `0x1800c036e`
- name: `?KerbGetHubTicketForAuthenticationTicket@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAU_KERB_EXTRA_CRED@@PEAU_KERB_PROXY_LOGON_CRED@@PEAU_UNICODE_STRING@@PEAU_KERB_TICKET_CACHE_ENTRY@@KPEAPEAU7@@Z`
- size: `590`
- prototype: `__int64 __fastcall(struct _KERB_LOGON_SESSION *, struct _KERB_CREDENTIAL *, struct _KERB_CREDMAN_CRED *, struct _KERB_EXTRA_CRED *, struct _KERB_PROXY_LOGON_CRED *, struct _UNICODE_STRING *, struct _KERB_TICKET_CACHE_ENTRY *, unsigned int, union _LARGE_INTEGER)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18003eb80`
- `0x180061e4c`

## callees

- `0x1800063e8`
- `0x18002a150`
- `0x180058f14`
- `0x18006cd70`
- `0x18006d240`
- `0x1800c0120`
- `0x1800c0374`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800c01b0`
- `ntdll!RtlReleaseResource` at `0x1800c01fa`
- `ntdll!RtlReleaseResource` at `0x1800c02a3`
- `ntdll!RtlReleaseResource` at `0x1800c02d8`
- `ntdll!RtlReleaseResource` at `0x1800c01b0`
- `ntdll!RtlReleaseResource` at `0x1800c01fa`
- `ntdll!RtlReleaseResource` at `0x1800c02a3`
- `ntdll!RtlReleaseResource` at `0x1800c02d8`
- `ntdll!RtlAcquireResourceShared` at `0x1800c0174`
- `ntdll!RtlAcquireResourceShared` at `0x1800c0174`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800c01d5`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800c027e`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800c01d5`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800c027e`

## pseudocode

```c

```
