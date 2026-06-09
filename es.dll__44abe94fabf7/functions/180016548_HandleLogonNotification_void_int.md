# HandleLogonNotification(void *,int)

- ea: `0x180016548`
- end: `0x180016676`
- name: `?HandleLogonNotification@@YAJPEAXH@Z`
- size: `302`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016c30`
- `0x180017df0`

## callees

- `0x180003d54`
- `0x1800161ec`
- `0x180016548`
- `0x180016680`
- `0x180016920`
- `0x180027aa0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016604`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016604`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001666e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800444eb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001666e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800444eb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001656d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001656d`

## string_xrefs

- `0x180016635`: `com\complus\src\events\tier2\service.cpp`

## pseudocode

```c

```
