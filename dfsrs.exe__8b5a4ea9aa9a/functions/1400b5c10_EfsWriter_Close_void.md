# EfsWriter::Close(void)

- ea: `0x1400b5c10`
- end: `0x1400b5d3e`
- name: `?Close@EfsWriter@@UEAAPEAVFrsStatus@@XZ`
- size: `302`
- prototype: `struct FrsStatus *__fastcall(EfsWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400b44b0`

## callees

- `0x14005c620`
- `0x1400b5c10`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetExitCodeThread` at `0x1400b5c87`
- `KERNEL32!GetExitCodeThread` at `0x1400b5c87`
- `KERNEL32!WaitForSingleObject` at `0x1400b5c41`
- `KERNEL32!WaitForSingleObject` at `0x1400b5c72`
- `KERNEL32!WaitForSingleObject` at `0x1400b5c41`
- `KERNEL32!WaitForSingleObject` at `0x1400b5c72`
- `KERNEL32!CloseHandle` at `0x1400b5c97`
- `KERNEL32!CloseHandle` at `0x1400b5c97`
- `KERNEL32!SetEvent` at `0x1400b5c60`
- `KERNEL32!SetEvent` at `0x1400b5c60`
- `KERNEL32!GetCurrentThreadId` at `0x1400b5ca8`
- `KERNEL32!GetCurrentThreadId` at `0x1400b5ca8`
- `ADVAPI32!CloseEncryptedFileRaw` at `0x1400b5d13`
- `ADVAPI32!CloseEncryptedFileRaw` at `0x1400b5d13`

## string_xrefs

- `0x1400b5ccb`: `EfsWriter::Close`

## pseudocode

```c

```
