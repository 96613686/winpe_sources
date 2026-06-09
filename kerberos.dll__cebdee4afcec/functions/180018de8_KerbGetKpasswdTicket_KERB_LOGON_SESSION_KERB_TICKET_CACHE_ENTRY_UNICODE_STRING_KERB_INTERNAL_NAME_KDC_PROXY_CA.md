# KerbGetKpasswdTicket(_KERB_LOGON_SESSION *,_KERB_TICKET_CACHE_ENTRY * *,_UNICODE_STRING *,_KERB_INTERNAL_NAME * *,_KDC_PROXY_CACHE_ENTRY * *)

- ea: `0x180018de8`
- end: `0x180019054`
- name: `?KerbGetKpasswdTicket@@YAJPEAU_KERB_LOGON_SESSION@@PEAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_UNICODE_STRING@@PEAPEAU_KERB_INTERNAL_NAME@@PEAPEAU_KDC_PROXY_CACHE_ENTRY@@@Z`
- size: `620`
- prototype: `int(struct _KERB_LOGON_SESSION *, struct _KERB_TICKET_CACHE_ENTRY **, struct _UNICODE_STRING *, struct _KERB_INTERNAL_NAME **, struct _KDC_PROXY_CACHE_ENTRY **)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800083b4`
- `0x1800b1f98`

## callees

- `0x1800068d0`
- `0x1800069e0`
- `0x180018de8`
- `0x1800190c0`
- `0x180019360`
- `0x180019678`
- `0x18006e748`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001900e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019038`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001900e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019038`
- `ntdll!RtlInitUnicodeString` at `0x180018e2c`
- `ntdll!RtlInitUnicodeString` at `0x180018e3d`
- `ntdll!RtlInitUnicodeString` at `0x180018e4e`
- `ntdll!RtlInitUnicodeString` at `0x180018e2c`
- `ntdll!RtlInitUnicodeString` at `0x180018e3d`
- `ntdll!RtlInitUnicodeString` at `0x180018e4e`
- `ntdll!RtlEnterCriticalSection` at `0x180018e8b`
- `ntdll!RtlEnterCriticalSection` at `0x180018e8b`
- `ntdll!RtlLeaveCriticalSection` at `0x180018ecf`
- `ntdll!RtlLeaveCriticalSection` at `0x180018ecf`

## pseudocode

```c

```
