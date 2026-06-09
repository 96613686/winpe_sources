# KerbLocateTicketCacheEntryByRealm(_KERB_TICKET_CACHE *,_UNICODE_STRING *,ulong)

- ea: `0x180037aa0`
- end: `0x180037c3d`
- name: `?KerbLocateTicketCacheEntryByRealm@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_UNICODE_STRING@@K@Z`
- size: `413`
- prototype: `struct _KERB_TICKET_CACHE_ENTRY *(struct _KERB_TICKET_CACHE *, struct _UNICODE_STRING *, unsigned int)`
- caller_count: `13`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000b430`
- `0x18003e488`
- `0x180041178`
- `0x18004969c`
- `0x18004ed20`
- `0x1800566a8`
- `0x18005b210`
- `0x1800872a0`
- `0x18008e4f4`
- `0x1800a56e0`
- `0x1800abf4c`
- `0x1800ac4b4`
- `0x1800c72d0`

## callees

- `0x1800063e8`
- `0x18002a150`
- `0x180037aa0`
- `0x18006557c`
- `0x180066994`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180037b33`
- `ntdll!RtlEqualUnicodeString` at `0x180037b4c`
- `ntdll!RtlEqualUnicodeString` at `0x180037b33`
- `ntdll!RtlEqualUnicodeString` at `0x180037b4c`
- `ntdll!RtlReleaseResource` at `0x180037bd8`
- `ntdll!RtlReleaseResource` at `0x180037bd8`
- `ntdll!RtlAcquireResourceShared` at `0x180037ad2`
- `ntdll!RtlAcquireResourceShared` at `0x180037ad2`
- `ntdll!RtlEnterCriticalSection` at `0x180037b11`
- `ntdll!RtlEnterCriticalSection` at `0x180037b11`
- `ntdll!RtlLeaveCriticalSection` at `0x180037b7a`
- `ntdll!RtlLeaveCriticalSection` at `0x180037bc1`
- `ntdll!RtlLeaveCriticalSection` at `0x180037b7a`
- `ntdll!RtlLeaveCriticalSection` at `0x180037bc1`

## pseudocode

```c

```
