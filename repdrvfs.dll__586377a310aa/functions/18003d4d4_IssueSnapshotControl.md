# _IssueSnapshotControl

- ea: `0x18003d4d4`
- end: `0x18003d5e0`
- name: `_IssueSnapshotControl`
- size: `268`
- prototype: `__int64 __fastcall(HANDLE FileHandle, unsigned int *, size_t Size)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180039c74`

## callees

- `0x18003d4d4`
- `0x1800443df`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5c0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d568`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d568`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d4ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d4ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d575`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d575`
- `ntdll!NtFsControlFile` at `0x18003d551`
- `ntdll!NtFsControlFile` at `0x18003d551`

## pseudocode

```c

```
