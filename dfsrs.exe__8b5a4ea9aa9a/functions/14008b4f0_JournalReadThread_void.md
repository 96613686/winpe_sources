# JournalReadThread(void *)

- ea: `0x14008b4f0`
- end: `0x14008b8ff`
- name: `?JournalReadThread@@YAKPEAX@Z`
- size: `1039`
- prototype: `unsigned int __fastcall(struct ChangeJournal::Group *)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x14000bbc5`
- `0x14000cb00`
- `0x14000e34c`
- `0x14001c264`
- `0x14002c2f4`
- `0x14008a208`
- `0x14008a754`
- `0x14008b370`
- `0x14008b4f0`
- `0x14008bda0`
- `0x14008c170`
- `0x14008c2e0`
- `0x14008dde4`
- `0x1401b30b0`
- `0x1401b9494`
- `0x1401bf49c`
- `0x1401bf590`

## import_xrefs

- `KERNEL32!GetQueuedCompletionStatus` at `0x14008b551`
- `KERNEL32!GetQueuedCompletionStatus` at `0x14008b551`
- `KERNEL32!CancelIo` at `0x14008b8b7`
- `KERNEL32!CancelIo` at `0x14008b8b7`
- `KERNEL32!GetLastError` at `0x14008b57e`
- `KERNEL32!GetLastError` at `0x14008b57e`
- `KERNEL32!SetEvent` at `0x14008b68f`
- `KERNEL32!SetEvent` at `0x14008b7c1`
- `KERNEL32!SetEvent` at `0x14008b68f`
- `KERNEL32!SetEvent` at `0x14008b7c1`
- `KERNEL32!GetCurrentThreadId` at `0x14008b5a9`
- `KERNEL32!GetCurrentThreadId` at `0x14008b5a9`

## string_xrefs

- `0x14008b5c6`: `JournalReadThread`
- `0x14008b61a`: `JournalReadThread`
- `0x14008b84c`: `JournalReadThread`
- `0x14008b642`: `Failed in GetQueuedCompletionStatus, Journal thread exiting. Error:%d`
- `0x14008b892`: `Forced UsnConsumer to commit. volId:%? volPath:%?`

## pseudocode

```c

```
