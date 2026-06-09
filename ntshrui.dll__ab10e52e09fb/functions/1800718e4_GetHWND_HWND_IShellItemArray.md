# GetHWND(HWND__ *,IShellItemArray *)

- ea: `0x1800718e4`
- end: `0x1800719bd`
- name: `?GetHWND@@YAPEAUHWND__@@PEAU1@PEAUIShellItemArray@@@Z`
- size: `217`
- prototype: `HWND __fastcall(HWND, struct IShellItemArray *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180071cf0`

## callees

- `0x18004ed88`
- `0x18004ef08`
- `0x18004f004`
- `0x1800718e4`
- `0x180072f84`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071996`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071996`
- `SHELL32!SHParseDisplayName` at `0x18007195d`
- `SHELL32!SHParseDisplayName` at `0x18007195d`
- `SHELL32!__imp_ILFree` at `0x180071988`
- `SHELL32!__imp_ILFree` at `0x180071988`

## pseudocode

```c

```
