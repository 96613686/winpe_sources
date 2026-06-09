# lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)

- ea: `0x180098070`
- end: `0x1800982a3`
- name: `?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z`
- size: `563`
- prototype: `__int64 __fastcall(unsigned __int8 *, HKEY *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002c940`
- `0x180098f34`

## callees

- `0x180097e60`
- `0x180097fa8`
- `0x180098070`
- `0x18009db94`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098151`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009821b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180098253`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009821b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180098253`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009813d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009813d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009826d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009826d`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x1800981df`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x1800981df`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x18009816d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x18009816d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x180098108`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x180098108`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800981b1`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800981b1`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18009811f`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180098184`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18009811f`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180098184`

## pseudocode

```c

```
