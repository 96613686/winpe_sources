# FileUtil::OpenForDelete(VolumeId const &,void *,FileId const &,void * &)

- ea: `0x1400bfd74`
- end: `0x1400c0070`
- name: `?OpenForDelete@FileUtil@@SAPEAVFrsStatus@@AEBVVolumeId@@PEAXAEBVFileId@@AEAPEAX@Z`
- size: `764`
- prototype: `struct FrsStatus *__fastcall(const struct VolumeId *, void *, const struct FileId *, void **)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1400b21f0`
- `0x1400bdcdc`

## callees

- `0x1400036a0`
- `0x14000ee94`
- `0x1400248f4`
- `0x14005c620`
- `0x1400bdf34`
- `0x1400be540`
- `0x1400be908`
- `0x1400bef20`
- `0x1400bf3b8`
- `0x1400bf870`
- `0x1400bfd74`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400bfe64`
- `KERNEL32!GetCurrentThreadId` at `0x1400bff03`
- `KERNEL32!GetCurrentThreadId` at `0x1400bfff7`
- `KERNEL32!GetCurrentThreadId` at `0x1400bfe64`
- `KERNEL32!GetCurrentThreadId` at `0x1400bff03`
- `KERNEL32!GetCurrentThreadId` at `0x1400bfff7`
- `ntdll!RtlNtStatusToDosError` at `0x1400bfe74`
- `ntdll!RtlNtStatusToDosError` at `0x1400bff13`
- `ntdll!RtlNtStatusToDosError` at `0x1400bfe74`
- `ntdll!RtlNtStatusToDosError` at `0x1400bff13`
- `ntdll!NtSetInformationFile` at `0x1400bfef5`
- `ntdll!NtSetInformationFile` at `0x1400bfef5`
- `ntdll!NtQueryInformationFile` at `0x1400bfe56`
- `ntdll!NtQueryInformationFile` at `0x1400bfe56`

## string_xrefs

- `0x1400bfdfa`: `FileUtil::OpenForDelete`

## pseudocode

```c

```
