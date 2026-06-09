# CompressedStreamDump::ParallelDumpTask::WaitForBucketWriteComplete(void)

- ea: `0x180412c28`
- end: `0x180412d06`
- name: `?WaitForBucketWriteComplete@ParallelDumpTask@CompressedStreamDump@@QEAA_NXZ`
- size: `222`
- prototype: `bool __fastcall(CompressedStreamDump::ParallelDumpTask *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180412578`
- `0x180412690`

## callees

- `0x180411be8`
- `0x180412c28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180412c45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180412c45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180412c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180412cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180412ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180412c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180412cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180412ce8`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180412ca4`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180412ca4`

## string_xrefs

- `0x180412c77`: `Task %u: WaitForBucketWriteComplete timeout after %u seconds.\n`
- `0x180412cf4`: `Task %u: GetOverlappedResult bytesWritten not equal to bytesToWrite. GetLastError: %u\n`
- `0x180412cc0`: `Task %u: GetOverlappedResult returned false. GetLastError: %u\n`
- `0x180412c68`: `Task %u: WaitForBucketWriteComplete->WaitForSingleObject returned error: %u.\n`

## pseudocode

```c

```
