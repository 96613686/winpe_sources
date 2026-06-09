# CPipeVCMgr::CreateVirtualChannel(IRDPCoreChannelManager *,char *,ulong,void * *)

- ea: `0x180016270`
- end: `0x180016538`
- name: `?CreateVirtualChannel@CPipeVCMgr@@UEAAJPEAUIRDPCoreChannelManager@@PEADKPEAPEAX@Z`
- size: `712`
- prototype: `__int64 __fastcall(CPipeVCMgr *__hidden this, struct IRDPCoreChannelManager *, char *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800091a8`
- `0x180012200`
- `0x180016270`
- `0x180016540`
- `0x180016804`
- `0x18002e600`
- `0x180033da0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800164f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800164f0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800162d3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800162d3`
- `RDPBASE!PAL_System_CritSecEnter` at `0x1800162ea`
- `RDPBASE!PAL_System_CritSecEnter` at `0x1800162ea`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800163f0`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800163f0`

## string_xrefs

- `0x1800163a7`: `PipeVC_CreateInstance<CPipeVC> failed!`
- `0x1800164a0`: `Failed to create VC handle using VC Pipe Object`

## pseudocode

```c

```
