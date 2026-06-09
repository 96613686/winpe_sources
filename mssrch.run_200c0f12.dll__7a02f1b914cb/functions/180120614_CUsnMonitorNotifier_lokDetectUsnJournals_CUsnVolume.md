# CUsnMonitorNotifier::lokDetectUsnJournals(CUsnVolume *)

- ea: `0x180120614`
- end: `0x180120a16`
- name: `?lokDetectUsnJournals@CUsnMonitorNotifier@@AEAAJPEAVCUsnVolume@@@Z`
- size: `1026`
- prototype: `int(CUsnMonitorNotifier *__hidden this, struct CUsnVolume *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800e7468`

## callees

- `0x180019bb0`
- `0x180022710`
- `0x18004e5d8`
- `0x18005e788`
- `0x18006028c`
- `0x1800604a0`
- `0x180061f78`
- `0x180120614`
- `0x1801244c0`
- `0x18012540e`
- `0x18021bd38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012067e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012067e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012075c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801207f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012081d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801208f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012075c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801207f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012081d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801208f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120976`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18012077d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180120813`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180120912`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180120997`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18012077d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180120813`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180120912`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180120997`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18012074c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801207ec`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801208e7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18012096c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18012074c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801207ec`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801208e7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18012096c`

## string_xrefs

- `0x180120695`: `[SrchGatherDirMon] DetectUsnJournals: Unable to create event`
- `0x18012078e`: `[SrchGatherDirMon] DetectUsnJournals: Cannot receive notification of journal delete on volume %ws`
- `0x1801208a5`: `[SrchGatherDirMon] DetectUsnJournals: Create journal on volume %ws`
- `0x180120705`: `[SrchGatherDirMon] DetectUsnJournals: Is Delete journal in progress on volume %ws?`

## pseudocode

```c

```
