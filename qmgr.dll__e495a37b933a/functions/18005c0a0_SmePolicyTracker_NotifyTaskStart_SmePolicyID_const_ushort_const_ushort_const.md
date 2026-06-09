# SmePolicyTracker::NotifyTaskStart(SmePolicyID const &,ushort const *,ushort const *)

- ea: `0x18005c0a0`
- end: `0x18005c430`
- name: `?NotifyTaskStart@SmePolicyTracker@@QEAAJAEBUSmePolicyID@@PEBG1@Z`
- size: `912`
- prototype: `__int64 __fastcall(SmePolicyTracker *__hidden this, const struct SmePolicyID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001dad4`
- `0x1800f2844`

## callees

- `0x18005c0a0`
- `0x180081600`
- `0x180090524`
- `0x18009bc50`
- `0x18009d024`
- `0x1800ab7b0`
- `0x1800ab7fc`
- `0x1800b1160`
- `0x1800e912c`
- `0x1800e91f8`
- `0x1800e9654`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18005c239`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18005c245`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18005c24f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18005c239`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18005c245`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18005c24f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c18e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c18e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c32e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c32e`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityStart` at `0x18005c224`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityStart` at `0x18005c224`

## pseudocode

```c

```
