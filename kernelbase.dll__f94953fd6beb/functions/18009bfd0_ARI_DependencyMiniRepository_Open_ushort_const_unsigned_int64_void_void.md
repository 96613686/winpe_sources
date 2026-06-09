# ARI::DependencyMiniRepository::Open(ushort const *,unsigned __int64 *,void * *,void * *)

- ea: `0x18009bfd0`
- end: `0x18009c1ce`
- name: `?Open@DependencyMiniRepository@ARI@@YAJPEBGPEA_KPEAPEAX2@Z`
- size: `510`
- prototype: `__int64 __fastcall(struct _EVENT_DATA_DESCRIPTOR *this, const unsigned __int16 *, unsigned __int64 *, void **, void **)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180033e24`
- `0x1800342c8`
- `0x18009ba40`
- `0x1800b7190`
- `0x18010d1a0`
- `0x1801138e0`
- `0x18014eab0`

## callees

- `0x180032f18`
- `0x1800486a0`
- `0x18009b400`
- `0x18009bfd0`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18009c16b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18009c16b`
- `ntdll!NtCreateSection` at `0x18009c050`
- `ntdll!NtCreateSection` at `0x18009c050`
- `ntdll!NtMapViewOfSection` at `0x18009c0b8`
- `ntdll!NtMapViewOfSection` at `0x18009c0b8`
- `ntdll!NtClose` at `0x18009c05b`
- `ntdll!NtClose` at `0x18009c163`
- `ntdll!NtClose` at `0x18009c1b3`
- `ntdll!NtClose` at `0x18009c1c6`
- `ntdll!NtClose` at `0x18009c05b`
- `ntdll!NtClose` at `0x18009c163`
- `ntdll!NtClose` at `0x18009c1b3`
- `ntdll!NtClose` at `0x18009c1c6`
- `ntdll!NtUnmapViewOfSection` at `0x18009c199`
- `ntdll!NtUnmapViewOfSection` at `0x18009c199`

## pseudocode

```c

```
