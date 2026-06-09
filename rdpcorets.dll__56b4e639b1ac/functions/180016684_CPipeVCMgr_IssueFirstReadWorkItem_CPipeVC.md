# CPipeVCMgr::IssueFirstReadWorkItem(CPipeVC *)

- ea: `0x180016684`
- end: `0x1800167fc`
- name: `?IssueFirstReadWorkItem@CPipeVCMgr@@QEAAJPEAVCPipeVC@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(CPipeVCMgr *this, struct CPipeVC *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800097d0`

## callees

- `0x1800091a8`
- `0x180012200`
- `0x180016684`
- `0x180016804`
- `0x18002e600`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800167bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800167bf`
- `RDPBASE!PAL_System_CritSecEnter` at `0x1800166ab`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001673a`
- `RDPBASE!PAL_System_CritSecEnter` at `0x1800166ab`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001673a`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800167d3`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800167e7`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800167d3`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800167e7`

## string_xrefs

- `0x18001677d`: `m_FirstReadWorkItemList.Add`

## pseudocode

```c

```
