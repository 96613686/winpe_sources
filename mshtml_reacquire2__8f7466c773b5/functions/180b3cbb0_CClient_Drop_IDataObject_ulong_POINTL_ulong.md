# CClient::Drop(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x180b3cbb0`
- end: `0x180b3cf21`
- name: `?Drop@CClient@@UEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `881`
- prototype: `__int64 __fastcall(CClient *__hidden this, struct IDataObject *, unsigned int, struct _POINTL, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x1800ea428`
- `0x18040ac58`
- `0x180b3cbb0`
- `0x180b3cf28`
- `0x180b3d758`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x180b3ccea`
- `KERNEL32!GlobalLock` at `0x180b3ccea`
- `KERNEL32!GlobalUnlock` at `0x180b3ce5d`
- `KERNEL32!GlobalUnlock` at `0x180b3ce5d`
- `KERNEL32!MultiByteToWideChar` at `0x180b3ce4e`
- `KERNEL32!MultiByteToWideChar` at `0x180b3ce4e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x180b3cd3d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x180b3cd3d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180b3cd53`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180b3cd53`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b3ce13`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b3ce13`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x180b3cd8a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x180b3cd8a`
- `ole32!ReleaseStgMedium` at `0x180b3ceb4`
- `ole32!ReleaseStgMedium` at `0x180b3ceb4`
- `SHELL32!DragQueryFileW` at `0x180b3cd2d`
- `SHELL32!DragQueryFileW` at `0x180b3cd2d`

## pseudocode

```c

```
