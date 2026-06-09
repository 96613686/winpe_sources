# NtfsFileSystem::SetAttributes(VolumeId const &,FileId const &,ushort const *,ulong,Usn &)

- ea: `0x1400b27e0`
- end: `0x1400b2aaf`
- name: `?SetAttributes@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@PEBGKAEAVUsn@@@Z`
- size: `719`
- prototype: `struct FrsStatus *__fastcall(NtfsFileSystem *__hidden this, const struct VolumeId *, const struct FileId *, const unsigned __int16 *, unsigned int, struct Usn *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x14010dba0`

## callees

- `0x1400036a0`
- `0x14000cc64`
- `0x140089c5c`
- `0x1400b27e0`
- `0x1400bf3b8`
- `0x1400bf79c`
- `0x1400c1340`
- `0x1400c1460`
- `0x1400c1f50`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400b28e4`
- `KERNEL32!GetCurrentThreadId` at `0x1400b29c1`
- `KERNEL32!GetCurrentThreadId` at `0x1400b2a31`
- `KERNEL32!GetCurrentThreadId` at `0x1400b28e4`
- `KERNEL32!GetCurrentThreadId` at `0x1400b29c1`
- `KERNEL32!GetCurrentThreadId` at `0x1400b2a31`
- `ntdll!RtlNtStatusToDosError` at `0x1400b28f4`
- `ntdll!RtlNtStatusToDosError` at `0x1400b29d1`
- `ntdll!RtlNtStatusToDosError` at `0x1400b28f4`
- `ntdll!RtlNtStatusToDosError` at `0x1400b29d1`
- `ntdll!NtSetInformationFile` at `0x1400b29b3`
- `ntdll!NtSetInformationFile` at `0x1400b29b3`
- `ntdll!NtQueryInformationFile` at `0x1400b28d6`
- `ntdll!NtQueryInformationFile` at `0x1400b28d6`

## pseudocode

```c

```
