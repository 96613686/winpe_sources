# ARI::DependencyMiniRepository::Open(ushort const *,unsigned __int64 *,void * *,void * *)

- ea: `0x18001552c`
- end: `0x18001575b`
- name: `?Open@DependencyMiniRepository@ARI@@YAJPEBGPEA_KPEAPEAX2@Z`
- size: `559`
- prototype: `__int64 __fastcall(struct _EVENT_DATA_DESCRIPTOR *this, const unsigned __int16 *, unsigned __int64 *, void **, void **)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180015764`
- `0x180019404`
- `0x1800198b8`
- `0x180115268`
- `0x180116430`
- `0x18011cf80`
- `0x1801594c0`

## callees

- `0x18000fb1c`
- `0x18001552c`
- `0x1800183d4`
- `0x180053330`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800156e0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800156e0`
- `ntdll!NtCreateSection` at `0x1800155ac`
- `ntdll!NtCreateSection` at `0x1800155ac`
- `ntdll!NtMapViewOfSection` at `0x180015620`
- `ntdll!NtMapViewOfSection` at `0x180015620`
- `ntdll!NtClose` at `0x1800155bd`
- `ntdll!NtClose` at `0x1800156d2`
- `ntdll!NtClose` at `0x180015734`
- `ntdll!NtClose` at `0x18001574d`
- `ntdll!NtClose` at `0x1800155bd`
- `ntdll!NtClose` at `0x1800156d2`
- `ntdll!NtClose` at `0x180015734`
- `ntdll!NtClose` at `0x18001574d`
- `ntdll!NtUnmapViewOfSection` at `0x180015714`
- `ntdll!NtUnmapViewOfSection` at `0x180015714`

## pseudocode

```c

```
