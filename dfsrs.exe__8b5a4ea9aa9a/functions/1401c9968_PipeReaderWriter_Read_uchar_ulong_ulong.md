# PipeReaderWriter::Read(uchar *,ulong,ulong &)

- ea: `0x1401c9968`
- end: `0x1401c9b68`
- name: `?Read@PipeReaderWriter@@QEAAPEAVFrsStatus@@PEAEKAEAK@Z`
- size: `512`
- prototype: `struct FrsStatus *__fastcall(PipeReaderWriter *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1401599e0`
- `0x140175188`
- `0x14019ea80`

## callees

- `0x14000bbc5`
- `0x14000d980`
- `0x14000dcc0`
- `0x1401b9494`
- `0x1401c991c`
- `0x1401c9968`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1401c99e7`
- `KERNEL32!WaitForSingleObject` at `0x1401c99e7`
- `KERNEL32!LeaveCriticalSection` at `0x1401c99d4`
- `KERNEL32!LeaveCriticalSection` at `0x1401c99d4`
- `KERNEL32!ResetEvent` at `0x1401c9a8e`
- `KERNEL32!ResetEvent` at `0x1401c9a8e`
- `KERNEL32!SetEvent` at `0x1401c9a75`
- `KERNEL32!SetEvent` at `0x1401c9a75`
- `KERNEL32!GetCurrentThreadId` at `0x1401c9abd`
- `KERNEL32!GetCurrentThreadId` at `0x1401c9b0d`
- `KERNEL32!GetCurrentThreadId` at `0x1401c9abd`
- `KERNEL32!GetCurrentThreadId` at `0x1401c9b0d`

## string_xrefs

- `0x1401c9ad9`: `base\fs\remotefs\frs\src\util\pipereaderwriter.cpp`
- `0x1401c9ace`: `PipeReaderWriter::Read`

## pseudocode

```c

```
