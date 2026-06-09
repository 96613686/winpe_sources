# KerbLocateTicketCacheEntryEx(_KERB_TICKET_CACHE *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,ulong)

- ea: `0x1800376ec`
- end: `0x180037894`
- name: `?KerbLocateTicketCacheEntryEx@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@K@Z`
- size: `424`
- prototype: `struct _KERB_TICKET_CACHE_ENTRY *(struct _KERB_TICKET_CACHE *, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *, unsigned int)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18003eb80`
- `0x18004ed20`
- `0x1800566a8`
- `0x18006250c`
- `0x1800a56e0`
- `0x1800cb5b8`

## callees

- `0x1800063e8`
- `0x180010030`
- `0x18002a150`
- `0x1800376ec`
- `0x18006557c`
- `0x180066994`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800377ab`
- `ntdll!RtlEqualUnicodeString` at `0x1800377bf`
- `ntdll!RtlEqualUnicodeString` at `0x1800377ab`
- `ntdll!RtlEqualUnicodeString` at `0x1800377bf`
- `ntdll!RtlReleaseResource` at `0x18003782d`
- `ntdll!RtlReleaseResource` at `0x18003782d`
- `ntdll!RtlAcquireResourceShared` at `0x180037726`
- `ntdll!RtlAcquireResourceShared` at `0x180037726`
- `ntdll!RtlEnterCriticalSection` at `0x180037764`
- `ntdll!RtlEnterCriticalSection` at `0x180037764`
- `ntdll!RtlLeaveCriticalSection` at `0x1800377eb`
- `ntdll!RtlLeaveCriticalSection` at `0x180037816`
- `ntdll!RtlLeaveCriticalSection` at `0x1800377eb`
- `ntdll!RtlLeaveCriticalSection` at `0x180037816`

## pseudocode

```c

```
