# NtfsFileSystem::GetFileInfo(VolumeId const &,FileId const &,ushort const *,Usn *,FileId *,FilePath *,_BY_HANDLE_FILE_INFORMATION *,_FILE_BASIC_INFORMATION *)

- ea: `0x1400af620`
- end: `0x1400af87d`
- name: `?GetFileInfo@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@PEBGPEAVUsn@@PEAV4@PEAVFilePath@@PEAU_BY_HANDLE_FILE_INFORMATION@@PEAU_FILE_BASIC_INFORMATION@@@Z`
- size: `605`
- prototype: `struct FrsStatus *(NtfsFileSystem *__hidden this, const struct VolumeId *, const struct FileId *, const unsigned __int16 *, struct Usn *, struct FileId *, struct FilePath *, struct _BY_HANDLE_FILE_INFORMATION *, struct _FILE_BASIC_INFORMATION *)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140032a14`
- `0x14011694c`
- `0x140180684`

## callees

- `0x14005c620`
- `0x140089c5c`
- `0x1400af620`
- `0x1400bef20`
- `0x1400bf79c`
- `0x1400bfbc0`
- `0x1400c03ec`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetFileInformationByHandle` at `0x1400af70b`
- `KERNEL32!GetFileInformationByHandle` at `0x1400af70b`
- `KERNEL32!GetLastError` at `0x1400af729`
- `KERNEL32!GetLastError` at `0x1400af729`
- `KERNEL32!GetCurrentThreadId` at `0x1400af71b`
- `KERNEL32!GetCurrentThreadId` at `0x1400af7b4`
- `KERNEL32!GetCurrentThreadId` at `0x1400af80c`
- `KERNEL32!GetCurrentThreadId` at `0x1400af71b`
- `KERNEL32!GetCurrentThreadId` at `0x1400af7b4`
- `KERNEL32!GetCurrentThreadId` at `0x1400af80c`
- `ntdll!RtlNtStatusToDosError` at `0x1400af7c4`
- `ntdll!RtlNtStatusToDosError` at `0x1400af7c4`
- `ntdll!NtQueryInformationFile` at `0x1400af7a6`
- `ntdll!NtQueryInformationFile` at `0x1400af7a6`

## pseudocode

```c

```
