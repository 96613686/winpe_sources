# DfsRemoveKnownDirectoryPath(_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x140018dbc`
- end: `0x140018e82`
- name: `?DfsRemoveKnownDirectoryPath@@YAKPEAU_UNICODE_STRING@@0@Z`
- size: `198`
- prototype: `unsigned int __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140028098`
- `0x14002e1b8`

## callees

- `0x140018dbc`
- `0x14005b158`
- `0x14005b648`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140018e64`
- `ntdll!RtlNtStatusToDosError` at `0x140018e64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140018dec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140018dec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140018e52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140018e52`

## pseudocode

```c

```
