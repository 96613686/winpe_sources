# KerbGetTicketGrantingTicket(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,_KERB_EXTRA_CRED *,_KERB_PROXY_LOGON_CRED *,_UNICODE_STRING *,ulong,_KERB_TICKET_CACHE_ENTRY * *,_KERB_ENCRYPTION_KEY *,uchar)

- ea: `0x180058f14`
- end: `0x180059bbb`
- name: `?KerbGetTicketGrantingTicket@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAU_KERB_EXTRA_CRED@@PEAU_KERB_PROXY_LOGON_CRED@@PEAU_UNICODE_STRING@@KPEAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_ENCRYPTION_KEY@@E@Z`
- size: `3239`
- prototype: `__int64 __usercall@<rax>(struct _KERB_LOGON_SESSION *@<rcx>, struct _KERB_CREDENTIAL *@<rdx>, struct _KERB_CREDMAN_CRED *@<r8>, struct _KERB_EXTRA_CRED *@<r9>, struct _KERB_PROXY_LOGON_CRED *, struct _UNICODE_STRING *, unsigned int, struct _KERB_TICKET_CACHE_ENTRY **, struct _KERB_ENCRYPTION_KEY *, unsigned __int8)`
- caller_count: `6`
- callee_count: `21`
- tags: `loader_planting`

## callers

- `0x18000b5c0`
- `0x180025680`
- `0x1800566a8`
- `0x1800627b0`
- `0x1800a5ed0`
- `0x1800c0120`

## callees

- `0x1800063e8`
- `0x1800068d0`
- `0x1800069e0`
- `0x18000b300`
- `0x1800190c0`
- `0x180019360`
- `0x180019678`
- `0x1800306c8`
- `0x180036ffc`
- `0x18003ca2c`
- `0x180048390`
- `0x180051450`
- `0x180058f14`
- `0x180059cec`
- `0x180060ce4`
- `0x18006ba6c`
- `0x18008a304`
- `0x18008b70c`
- `0x18009e488`
- `0x1800aebbc`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059442`
- `ntdll!RtlEqualUnicodeString` at `0x180059488`
- `ntdll!RtlEqualUnicodeString` at `0x1800594a1`
- `ntdll!RtlEqualUnicodeString` at `0x1800595d1`
- `ntdll!RtlEqualUnicodeString` at `0x1800595ea`
- `ntdll!RtlEqualUnicodeString` at `0x180059799`
- `ntdll!RtlEqualUnicodeString` at `0x180059488`
- `ntdll!RtlEqualUnicodeString` at `0x1800594a1`
- `ntdll!RtlEqualUnicodeString` at `0x1800595d1`
- `ntdll!RtlEqualUnicodeString` at `0x1800595ea`
- `ntdll!RtlEqualUnicodeString` at `0x180059799`
- `ntdll!RtlEnterCriticalSection` at `0x180058f92`
- `ntdll!RtlEnterCriticalSection` at `0x18005933e`
- `ntdll!RtlEnterCriticalSection` at `0x1800593db`
- `ntdll!RtlEnterCriticalSection` at `0x18005954b`
- `ntdll!RtlEnterCriticalSection` at `0x180059680`
- `ntdll!RtlEnterCriticalSection` at `0x180059725`
- `ntdll!RtlEnterCriticalSection` at `0x1800599f4`
- `ntdll!RtlEnterCriticalSection` at `0x180058f92`
- `ntdll!RtlEnterCriticalSection` at `0x18005933e`
- `ntdll!RtlEnterCriticalSection` at `0x1800593db`
- `ntdll!RtlEnterCriticalSection` at `0x18005954b`
- `ntdll!RtlEnterCriticalSection` at `0x180059680`
- `ntdll!RtlEnterCriticalSection` at `0x180059725`
- `ntdll!RtlEnterCriticalSection` at `0x1800599f4`
- `ntdll!RtlLeaveCriticalSection` at `0x180059136`
- `ntdll!RtlLeaveCriticalSection` at `0x180059387`
- `ntdll!RtlLeaveCriticalSection` at `0x18005943c`
- `ntdll!RtlLeaveCriticalSection` at `0x18005946d`
- `ntdll!RtlLeaveCriticalSection` at `0x180059586`
- `ntdll!RtlLeaveCriticalSection` at `0x1800596af`
- `ntdll!RtlLeaveCriticalSection` at `0x180059771`
- `ntdll!RtlLeaveCriticalSection` at `0x1800599d2`
- `ntdll!RtlLeaveCriticalSection` at `0x180059a67`
- `ntdll!RtlLeaveCriticalSection` at `0x180059136`
- `ntdll!RtlLeaveCriticalSection` at `0x180059387`
- `ntdll!RtlLeaveCriticalSection` at `0x18005943c`
- `ntdll!RtlLeaveCriticalSection` at `0x18005946d`
- `ntdll!RtlLeaveCriticalSection` at `0x180059586`
- `ntdll!RtlLeaveCriticalSection` at `0x1800596af`
- `ntdll!RtlLeaveCriticalSection` at `0x180059771`
- `ntdll!RtlLeaveCriticalSection` at `0x1800599d2`
- `ntdll!RtlLeaveCriticalSection` at `0x180059a67`

## string_xrefs

- `0x180059b00`: `%hs: Showing Stale Cred Notification Balloon, Status 0x%x, BalloonType %x, CacheLogonFlags 0x%x, LogonSessionFlags 0x%x, UsedPrimaryLogonCreds %s, ProtectedUser %s\n`

## pseudocode

```c

```
