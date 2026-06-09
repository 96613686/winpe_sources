# KerbGetTgtToS4URealm(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_UNICODE_STRING *,_KERB_TICKET_CACHE_ENTRY * *,ulong,ulong,ulong)

- ea: `0x180057f58`
- end: `0x180058377`
- name: `?KerbGetTgtToS4URealm@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_UNICODE_STRING@@PEAPEAU_KERB_TICKET_CACHE_ENTRY@@KKK@Z`
- size: `1055`
- prototype: `__int64 __usercall@<rax>(struct _KERB_LOGON_SESSION *@<rcx>, struct _KERB_CREDENTIAL *@<rdx>, struct _UNICODE_STRING *@<r8>, struct _KERB_TICKET_CACHE_ENTRY **@<r9>, unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, service_task`

## callers

- `0x180054c88`
- `0x18009c9bc`

## callees

- `0x1800063e8`
- `0x1800068d0`
- `0x1800069e0`
- `0x1800113f0`
- `0x1800190c0`
- `0x180041178`
- `0x18004ed20`
- `0x180057f58`
- `0x180061e4c`
- `0x18008a304`
- `0x18008b70c`
- `0x180091118`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800580c2`
- `ntdll!RtlEqualUnicodeString` at `0x1800580ea`
- `ntdll!RtlEqualUnicodeString` at `0x1800580c2`
- `ntdll!RtlEqualUnicodeString` at `0x1800580ea`
- `ntdll!RtlEnterCriticalSection` at `0x180057fbd`
- `ntdll!RtlEnterCriticalSection` at `0x180058244`
- `ntdll!RtlEnterCriticalSection` at `0x180057fbd`
- `ntdll!RtlEnterCriticalSection` at `0x180058244`
- `ntdll!RtlLeaveCriticalSection` at `0x180058040`
- `ntdll!RtlLeaveCriticalSection` at `0x1800580ae`
- `ntdll!RtlLeaveCriticalSection` at `0x1800582af`
- `ntdll!RtlLeaveCriticalSection` at `0x180058040`
- `ntdll!RtlLeaveCriticalSection` at `0x1800580ae`
- `ntdll!RtlLeaveCriticalSection` at `0x1800582af`

## string_xrefs

- `0x180058317`: `Failed to get TGS ticket for service 0x%x`

## pseudocode

```c

```
