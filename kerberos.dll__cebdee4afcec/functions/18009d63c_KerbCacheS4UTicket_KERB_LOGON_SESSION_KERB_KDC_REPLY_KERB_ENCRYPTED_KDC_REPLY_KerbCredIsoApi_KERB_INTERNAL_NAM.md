# KerbCacheS4UTicket(_KERB_LOGON_SESSION *,KERB_KDC_REPLY *,KERB_ENCRYPTED_KDC_REPLY *,KerbCredIsoApi *,_KERB_INTERNAL_NAME *,_KERB_INTERNAL_NAME * *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,ulong,_KERB_TICKET_CACHE *,_UNICODE_STRING *,_KERB_TICKET_CACHE_ENTRY * *,_KERB_ENCRYPTION_KEY *)

- ea: `0x18009d63c`
- end: `0x18009da93`
- name: `?KerbCacheS4UTicket@@YAJPEAU_KERB_LOGON_SESSION@@PEAUKERB_KDC_REPLY@@PEAUKERB_ENCRYPTED_KDC_REPLY@@PEAVKerbCredIsoApi@@PEAU_KERB_INTERNAL_NAME@@PEAPEAU5@4PEAU_UNICODE_STRING@@KPEAU_KERB_TICKET_CACHE@@6PEAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_ENCRYPTION_KEY@@@Z`
- size: `1111`
- prototype: `__int64 __fastcall(struct _KERB_LOGON_SESSION *, struct KERB_KDC_REPLY *, struct KERB_ENCRYPTED_KDC_REPLY *, struct KerbCredIsoApi *, struct _KERB_INTERNAL_NAME *, struct _KERB_INTERNAL_NAME **, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *, unsigned int, struct _KERB_TICKET_CACHE *, struct _UNICODE_STRING *, struct _KERB_TICKET_CACHE_ENTRY **, struct _KERB_ENCRYPTION_KEY *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x180054c88`

## callees

- `0x180005f38`
- `0x1800063e8`
- `0x1800093f0`
- `0x18000b300`
- `0x180014d4c`
- `0x180016550`
- `0x180020e10`
- `0x1800210e0`
- `0x1800290c0`
- `0x18002bbf0`
- `0x180030ea8`
- `0x180058380`
- `0x18006557c`
- `0x180066ee0`
- `0x18008b70c`
- `0x18009d63c`
- `0x1800dd840`
- `0x1800ddac4`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x18009d697`
- `ntdll!RtlInitializeCriticalSection` at `0x18009d697`
- `ntdll!RtlEnterCriticalSection` at `0x18009d764`
- `ntdll!RtlEnterCriticalSection` at `0x18009d7e5`
- `ntdll!RtlEnterCriticalSection` at `0x18009d764`
- `ntdll!RtlEnterCriticalSection` at `0x18009d7e5`
- `ntdll!RtlLeaveCriticalSection` at `0x18009d78b`
- `ntdll!RtlLeaveCriticalSection` at `0x18009d806`
- `ntdll!RtlLeaveCriticalSection` at `0x18009d78b`
- `ntdll!RtlLeaveCriticalSection` at `0x18009d806`

## string_xrefs

- `0x18009d6cd`: `KerbCacheS4UTicket populating u2u SKEY\n`
- `0x18009d6ab`: `KerbCacheS4UTicket`
- `0x18009da25`: `Removing S4U Cache Entry - %p\n`

## pseudocode

```c

```
