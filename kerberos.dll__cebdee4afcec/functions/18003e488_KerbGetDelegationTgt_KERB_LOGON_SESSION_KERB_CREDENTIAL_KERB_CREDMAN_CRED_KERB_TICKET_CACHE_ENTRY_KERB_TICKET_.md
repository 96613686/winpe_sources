# KerbGetDelegationTgt(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,_KERB_TICKET_CACHE_ENTRY *,_KERB_TICKET_CACHE_ENTRY * *)

- ea: `0x18003e488`
- end: `0x18003e9cf`
- name: `?KerbGetDelegationTgt@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAU_KERB_TICKET_CACHE_ENTRY@@PEAPEAU4@@Z`
- size: `1351`
- prototype: `__int64 __fastcall(struct _KERB_LOGON_SESSION *, struct _KERB_CREDENTIAL *, struct _KERB_CREDMAN_CRED *, struct _KERB_TICKET_CACHE_ENTRY *, struct _KERB_TICKET_CACHE_ENTRY **)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003d7d0`

## callees

- `0x1800063e8`
- `0x1800068d0`
- `0x1800069e0`
- `0x1800113f0`
- `0x1800290c0`
- `0x180037aa0`
- `0x18003e488`
- `0x180040fb8`
- `0x180041178`
- `0x18004ed20`
- `0x180070680`
- `0x18007108c`
- `0x18008b70c`
- `0x1800dd798`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003e548`
- `ntdll!RtlInitUnicodeString` at `0x18003e548`
- `ntdll!RtlEnterCriticalSection` at `0x18003e89b`
- `ntdll!RtlEnterCriticalSection` at `0x18003e9a0`
- `ntdll!RtlEnterCriticalSection` at `0x18003e89b`
- `ntdll!RtlEnterCriticalSection` at `0x18003e9a0`
- `ntdll!NtQuerySystemTime` at `0x18003e584`
- `ntdll!NtQuerySystemTime` at `0x18003e584`
- `ntdll!RtlLeaveCriticalSection` at `0x18003e6e2`
- `ntdll!RtlLeaveCriticalSection` at `0x18003e6e2`
- `cryptdll!CDBuildIntegrityVect` at `0x18003e718`
- `cryptdll!CDBuildIntegrityVect` at `0x18003e718`

## string_xrefs

- `0x18003e67f`: `KerbGetTgtForService failed to get TGT: 0x%x`

## pseudocode

```c

```
