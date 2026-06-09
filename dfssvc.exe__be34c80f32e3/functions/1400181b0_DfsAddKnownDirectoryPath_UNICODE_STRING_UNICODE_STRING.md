# DfsAddKnownDirectoryPath(_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x1400181b0`
- end: `0x140018276`
- name: `?DfsAddKnownDirectoryPath@@YAKPEAU_UNICODE_STRING@@0@Z`
- size: `198`
- prototype: `unsigned int __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140028098`

## callees

- `0x1400181b0`
- `0x14005b158`
- `0x14005b2d0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140018258`
- `ntdll!RtlNtStatusToDosError` at `0x140018258`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400181e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400181e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140018246`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140018246`

## pseudocode

```c

```
