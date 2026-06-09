# THREAD_MANAGER::ParkThread(ulong,ulong,_OVERLAPPED *)

- ea: `0x1800212d0`
- end: `0x1800213d2`
- name: `?ParkThread@THREAD_MANAGER@@CAXKKPEAU_OVERLAPPED@@@Z`
- size: `258`
- prototype: `void __fastcall(unsigned int, unsigned int, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800212d0`
- `0x180022098`

## import_xrefs

- `KERNEL32!WaitForMultipleObjectsEx` at `0x180021370`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180021370`
- `iisutil!PuDbgPrint` at `0x180021322`
- `iisutil!PuDbgPrint` at `0x1800213ac`
- `iisutil!PuDbgPrint` at `0x180021322`
- `iisutil!PuDbgPrint` at `0x1800213ac`

## string_xrefs

- `0x18002131b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x1800213a5`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180021303`: `W3TP: Thread parking\n`
- `0x18002130a`: `THREAD_MANAGER::ParkThread`
- `0x180021393`: `THREAD_MANAGER::ParkThread`
- `0x18002138c`: `W3TP: Thread unparked\n`

## pseudocode

```c

```
