# LsaDbpLookupAwaitCompletionWorkList(_LSAP_DB_LOOKUP_WORK_LIST *)

- ea: `0x180032c50`
- end: `0x180032d31`
- name: `?LsaDbpLookupAwaitCompletionWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(struct _LSAP_DB_LOOKUP_WORK_LIST *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b8dc`

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x180032c50`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180032cbd`
- `ntdll!NtWaitForSingleObject` at `0x180032cbd`
- `ntdll!RtlLeaveCriticalSection` at `0x180032c83`
- `ntdll!RtlLeaveCriticalSection` at `0x180032c83`
- `ntdll!RtlEnterCriticalSection` at `0x180032c69`
- `ntdll!RtlEnterCriticalSection` at `0x180032c69`

## pseudocode

```c

```
