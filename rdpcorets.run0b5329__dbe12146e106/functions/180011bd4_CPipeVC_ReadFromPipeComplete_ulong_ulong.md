# CPipeVC::ReadFromPipeComplete(ulong,ulong)

- ea: `0x180011bd4`
- end: `0x18001209a`
- name: `?ReadFromPipeComplete@CPipeVC@@IEAAXKK@Z`
- size: `1222`
- prototype: `void __fastcall(CPipeVC *this, DWORD LastError, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180011ba0`

## callees

- `0x1800091a8`
- `0x18000a93c`
- `0x18000c8c0`
- `0x180011bd4`
- `0x180012200`
- `0x180016864`
- `0x180025884`
- `0x18002e600`
- `0x180032f60`
- `0x180075c6c`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011c15`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ce7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ce7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d22`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180011cd9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180011cd9`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180011c25`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180011dd3`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180011f7e`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180011c25`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180011dd3`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180011f7e`
- `RDPBASE!PAL_System_CritSecLeave` at `0x180011ca3`
- `RDPBASE!PAL_System_CritSecLeave` at `0x180011fed`
- `RDPBASE!PAL_System_CritSecLeave` at `0x180011ca3`
- `RDPBASE!PAL_System_CritSecLeave` at `0x180011fed`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x180011d18`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x180011d18`

## string_xrefs

- `0x180011ef1`: `IssueRead call failed`

## pseudocode

```c

```
