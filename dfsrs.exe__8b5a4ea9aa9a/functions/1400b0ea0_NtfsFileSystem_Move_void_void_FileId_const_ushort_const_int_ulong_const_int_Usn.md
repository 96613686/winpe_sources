# NtfsFileSystem::Move(void *,void *,FileId const &,ushort const *,int,ulong const *,int,Usn *)

- ea: `0x1400b0ea0`
- end: `0x1400b1177`
- name: `?Move@NtfsFileSystem@@QEAAPEAVFrsStatus@@PEAX0AEBVFileId@@PEBGHPEBKHPEAVUsn@@@Z`
- size: `727`
- prototype: `struct FrsStatus *(NtfsFileSystem *__hidden this, void *, void *, const struct FileId *, const unsigned __int16 *, int, const unsigned int *, int, struct Usn *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400b1180`
- `0x1400b13f0`

## callees

- `0x1400036a0`
- `0x14000cdc0`
- `0x14005c620`
- `0x1400b0ea0`
- `0x1400bf3b8`
- `0x1400bf870`
- `0x1400c0594`
- `0x1400c1340`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400b0f84`
- `KERNEL32!GetCurrentThreadId` at `0x1400b104a`
- `KERNEL32!GetCurrentThreadId` at `0x1400b110a`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0f84`
- `KERNEL32!GetCurrentThreadId` at `0x1400b104a`
- `KERNEL32!GetCurrentThreadId` at `0x1400b110a`
- `ntdll!RtlNtStatusToDosError` at `0x1400b0f94`
- `ntdll!RtlNtStatusToDosError` at `0x1400b105a`
- `ntdll!RtlNtStatusToDosError` at `0x1400b0f94`
- `ntdll!RtlNtStatusToDosError` at `0x1400b105a`
- `ntdll!NtSetInformationFile` at `0x1400b103c`
- `ntdll!NtSetInformationFile` at `0x1400b103c`
- `ntdll!NtQueryInformationFile` at `0x1400b0f76`
- `ntdll!NtQueryInformationFile` at `0x1400b0f76`

## string_xrefs

- `0x1400b0fb1`: `NtfsFileSystem::Move`
- `0x1400b1001`: `NtfsFileSystem::Move`
- `0x1400b10fa`: `Failed, but rename completed. Error:%?`
- `0x1400b10d3`: `NtfsFileSystem::Move`

## pseudocode

```c

```
