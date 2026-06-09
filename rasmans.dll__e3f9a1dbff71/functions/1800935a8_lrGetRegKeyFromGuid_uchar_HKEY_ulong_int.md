# lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)

- ea: `0x1800935a8`
- end: `0x180093798`
- name: `?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z`
- size: `496`
- prototype: `__int64 __fastcall(WCHAR *, HKEY *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002b6a0`
- `0x1800943c8`

## callees

- `0x1800933c4`
- `0x1800934ec`
- `0x1800935a8`
- `0x180098b18`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093677`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093723`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093755`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093723`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093755`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093669`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093669`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093769`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093769`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800936c5`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800936c5`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x18009368d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x18009368d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x180093640`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x180093640`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x1800936ed`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x1800936ed`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180093651`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18009369e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180093651`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18009369e`

## pseudocode

```c

```
