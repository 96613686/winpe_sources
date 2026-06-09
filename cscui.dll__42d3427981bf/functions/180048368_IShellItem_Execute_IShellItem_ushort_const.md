# IShellItem_Execute(IShellItem *,ushort const *)

- ea: `0x180048368`
- end: `0x180048403`
- name: `?IShellItem_Execute@@YAJPEAUIShellItem@@PEBG@Z`
- size: `155`
- prototype: `__int64 __fastcall(struct IShellItem *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180028ba0`

## callees

- `0x180008a7c`
- `0x180048368`
- `0x18004c636`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x1800483d5`
- `SHELL32!ShellExecuteExW` at `0x1800483d5`
- `SHELL32!SHGetIDListFromObject` at `0x180048383`
- `SHELL32!SHGetIDListFromObject` at `0x180048383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800483f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800483f2`

## pseudocode

```c

```
