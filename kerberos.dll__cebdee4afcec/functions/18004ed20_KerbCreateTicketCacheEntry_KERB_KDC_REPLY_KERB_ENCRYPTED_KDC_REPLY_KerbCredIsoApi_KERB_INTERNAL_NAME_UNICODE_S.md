# KerbCreateTicketCacheEntry(KERB_KDC_REPLY *,KERB_ENCRYPTED_KDC_REPLY *,KerbCredIsoApi *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,ulong,long,_KERB_TICKET_CACHE *,_KERB_ENCRYPTION_KEY *,_UNICODE_STRING *,_UNICODE_STRING *,unsigned __int64,_KERB_TICKET_CACHE_ENTRY * *)

- ea: `0x18004ed20`
- end: `0x18004f211`
- name: `?KerbCreateTicketCacheEntry@@YAJPEAUKERB_KDC_REPLY@@PEAUKERB_ENCRYPTED_KDC_REPLY@@PEAVKerbCredIsoApi@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@KJPEAU_KERB_TICKET_CACHE@@PEAU_KERB_ENCRYPTION_KEY@@44_KPEAPEAU_KERB_TICKET_CACHE_ENTRY@@@Z`
- size: `1265`
- prototype: `__int64 __fastcall(struct KERB_KDC_REPLY *, struct KERB_ENCRYPTED_KDC_REPLY *, struct KerbCredIsoApi *, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *, unsigned int, int, struct _KERB_TICKET_CACHE *, struct _KERB_ENCRYPTION_KEY *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int64, struct _KERB_TICKET_CACHE_ENTRY **)`
- caller_count: `16`
- callee_count: `21`
- tags: `loader_planting`

## callers

- `0x180019678`
- `0x18003e488`
- `0x18003eb80`
- `0x180041ff0`
- `0x180048f6c`
- `0x180054c88`
- `0x1800566a8`
- `0x180057f58`
- `0x180090068`
- `0x1800911f0`
- `0x18009c9bc`
- `0x1800a6410`
- `0x1800ab118`
- `0x1800ab94c`
- `0x1800bf958`
- `0x1800c0374`

## callees

- `0x180005f38`
- `0x1800063e8`
- `0x18000b300`
- `0x180016550`
- `0x180020690`
- `0x180020e10`
- `0x1800210e0`
- `0x1800290c0`
- `0x180029c50`
- `0x180030ea8`
- `0x180036094`
- `0x1800376ec`
- `0x180037aa0`
- `0x18004ed20`
- `0x18004fa28`
- `0x1800643dc`
- `0x18006557c`
- `0x180066ee0`
- `0x18007108c`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004eec1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004eec1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004ed86`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004ed86`
- `ntdll!RtlEqualUnicodeString` at `0x18004efe7`
- `ntdll!RtlEqualUnicodeString` at `0x18004efe7`
- `ntdll!RtlInitializeCriticalSection` at `0x18004edbd`
- `ntdll!RtlInitializeCriticalSection` at `0x18004edbd`

## string_xrefs

- `0x18004eeee`: `Tried to cache an already-expired ticket\n`
- `0x18004eefb`: `KerbCreateTicketCacheEntry`

## pseudocode

```c

```
