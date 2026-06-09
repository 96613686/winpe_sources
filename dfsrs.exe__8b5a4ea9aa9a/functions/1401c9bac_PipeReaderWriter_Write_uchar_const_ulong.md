# PipeReaderWriter::Write(uchar const *,ulong)

- ea: `0x1401c9bac`
- end: `0x1401c9da4`
- name: `?Write@PipeReaderWriter@@QEAAPEAVFrsStatus@@PEBEK@Z`
- size: `504`
- prototype: `struct FrsStatus *__fastcall(PipeReaderWriter *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1401587ec`
- `0x140159da0`
- `0x14019c720`
- `0x14019c930`

## callees

- `0x14000bbc5`
- `0x14000d980`
- `0x14000dcc0`
- `0x1401b9494`
- `0x1401c9bac`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1401c9c35`
- `KERNEL32!WaitForSingleObject` at `0x1401c9c35`
- `KERNEL32!LeaveCriticalSection` at `0x1401c9c22`
- `KERNEL32!LeaveCriticalSection` at `0x1401c9c22`
- `KERNEL32!ResetEvent` at `0x1401c9cca`
- `KERNEL32!ResetEvent` at `0x1401c9cca`
- `KERNEL32!SetEvent` at `0x1401c9cae`
- `KERNEL32!SetEvent` at `0x1401c9cae`
- `KERNEL32!GetCurrentThreadId` at `0x1401c9cf9`
- `KERNEL32!GetCurrentThreadId` at `0x1401c9d49`
- `KERNEL32!GetCurrentThreadId` at `0x1401c9cf9`
- `KERNEL32!GetCurrentThreadId` at `0x1401c9d49`

## string_xrefs

- `0x1401c9d15`: `base\fs\remotefs\frs\src\util\pipereaderwriter.cpp`
- `0x1401c9d0a`: `PipeReaderWriter::Write`

## pseudocode

```c

```
