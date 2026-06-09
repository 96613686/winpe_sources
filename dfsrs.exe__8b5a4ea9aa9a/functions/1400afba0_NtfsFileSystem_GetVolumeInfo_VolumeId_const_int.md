# NtfsFileSystem::GetVolumeInfo(VolumeId const &,int &)

- ea: `0x1400afba0`
- end: `0x1400afd89`
- name: `?GetVolumeInfo@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEAH@Z`
- size: `489`
- prototype: `struct FrsStatus *__fastcall(NtfsFileSystem *__hidden this, const struct VolumeId *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x1400036a0`
- `0x14005c620`
- `0x1400afba0`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1400afc06`
- `KERNEL32!CreateFileW` at `0x1400afc06`
- `KERNEL32!GetLastError` at `0x1400afcd4`
- `KERNEL32!GetLastError` at `0x1400afcd4`
- `KERNEL32!GetCurrentThreadId` at `0x1400afc70`
- `KERNEL32!GetCurrentThreadId` at `0x1400afcc6`
- `KERNEL32!GetCurrentThreadId` at `0x1400afd21`
- `KERNEL32!GetCurrentThreadId` at `0x1400afc70`
- `KERNEL32!GetCurrentThreadId` at `0x1400afcc6`
- `KERNEL32!GetCurrentThreadId` at `0x1400afd21`
- `ntdll!RtlNtStatusToDosError` at `0x1400afc81`
- `ntdll!RtlNtStatusToDosError` at `0x1400afc81`
- `ntdll!NtQueryVolumeInformationFile` at `0x1400afc3d`
- `ntdll!NtQueryVolumeInformationFile` at `0x1400afc3d`

## pseudocode

```c

```
