# CSharingConfiguration::_ShowShareItemsUI(HWND__ *,IShellItemArray *,IShellItemArray *,SHARE_ACTIVATION_MODE,CUserObject *)

- ea: `0x18005569c`
- end: `0x1800557ae`
- name: `?_ShowShareItemsUI@CSharingConfiguration@@AEAAJPEAUHWND__@@PEAUIShellItemArray@@1W4SHARE_ACTIVATION_MODE@@PEAVCUserObject@@@Z`
- size: `274`
- prototype: `int __high(HWND, struct IShellItemArray *, struct IShellItemArray *, enum SHARE_ACTIVATION_MODE, struct CUserObject *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054c50`
- `0x180054c80`
- `0x180054d60`
- `0x180054d90`

## callees

- `0x1800254e0`
- `0x18005569c`
- `0x180071f24`
- `0x180072f84`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180055743`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180055743`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055766`
- `SHELL32!__imp_SHObjectProperties` at `0x18005575b`
- `SHELL32!__imp_SHObjectProperties` at `0x18005575b`

## pseudocode

```c

```
