# NtfsFileSystem::SetAttributes(VolumeId const &,FileId const &,ulong,Usn &)

- ea: `0x1400b2520`
- end: `0x1400b27d9`
- name: `?SetAttributes@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@KAEAVUsn@@@Z`
- size: `697`
- prototype: `struct FrsStatus *__fastcall(NtfsFileSystem *__hidden this, const struct VolumeId *, const struct FileId *, unsigned int, struct Usn *)`
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x14010dba0`
- `0x14017fa28`
- `0x140187420`
- `0x14018b274`

## callees

- `0x1400036a0`
- `0x14000cc64`
- `0x14005c620`
- `0x140089c5c`
- `0x1400b2520`
- `0x1400bf3b8`
- `0x1400bf79c`
- `0x1400bf870`
- `0x1400c1340`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400b2623`
- `KERNEL32!GetCurrentThreadId` at `0x1400b26f6`
- `KERNEL32!GetCurrentThreadId` at `0x1400b2762`
- `KERNEL32!GetCurrentThreadId` at `0x1400b2623`
- `KERNEL32!GetCurrentThreadId` at `0x1400b26f6`
- `KERNEL32!GetCurrentThreadId` at `0x1400b2762`
- `ntdll!RtlNtStatusToDosError` at `0x1400b2633`
- `ntdll!RtlNtStatusToDosError` at `0x1400b2706`
- `ntdll!RtlNtStatusToDosError` at `0x1400b2633`
- `ntdll!RtlNtStatusToDosError` at `0x1400b2706`
- `ntdll!NtSetInformationFile` at `0x1400b26e8`
- `ntdll!NtSetInformationFile` at `0x1400b26e8`
- `ntdll!NtQueryInformationFile` at `0x1400b2615`
- `ntdll!NtQueryInformationFile` at `0x1400b2615`

## pseudocode

```c

```
