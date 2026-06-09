# FeedbackHubMonitorThread(void *)

- ea: `0x18007b720`
- end: `0x18007b821`
- name: `?FeedbackHubMonitorThread@@YAKPEAX@Z`
- size: `257`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180025070`
- `0x18007b454`
- `0x18007b720`
- `0x180094040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007b814`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007b814`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18007b73c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18007b73c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007b729`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007b729`

## string_xrefs

- `0x18007b75a`: `Monitor thread exiting because we have nothing to do.`
- `0x18007b7eb`: `Monitor thread: No activity running, ignoring`
- `0x18007b7a9`: `Monitor thread: Stopping escalation`

## pseudocode

```c

```
