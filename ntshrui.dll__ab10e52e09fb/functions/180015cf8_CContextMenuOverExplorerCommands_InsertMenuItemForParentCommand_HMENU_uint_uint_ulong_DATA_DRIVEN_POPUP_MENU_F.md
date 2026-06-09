# CContextMenuOverExplorerCommands::InsertMenuItemForParentCommand(HMENU__ *,uint,uint,ulong,DATA_DRIVEN_POPUP_MENU_FLAGS,ushort const *)

- ea: `0x180015cf8`
- end: `0x180015e65`
- name: `?InsertMenuItemForParentCommand@CContextMenuOverExplorerCommands@@AEAA_NPEAUHMENU__@@IIKW4DATA_DRIVEN_POPUP_MENU_FLAGS@@PEBG@Z`
- size: `365`
- prototype: `bool __high(HMENU, unsigned int, unsigned int, unsigned int, enum DATA_DRIVEN_POPUP_MENU_FLAGS, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014920`

## callees

- `0x180015cf8`
- `0x180023280`
- `0x1800232a0`
- `0x180026394`
- `0x180078010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180015df1`
- `GDI32!DeleteObject` at `0x180015df1`
- `USER32!SetMenuItemBitmaps` at `0x180015e33`
- `USER32!SetMenuItemBitmaps` at `0x180015e33`
- `USER32!InsertMenuItemW` at `0x180015d68`
- `USER32!InsertMenuItemW` at `0x180015d68`
- `USER32!GetSystemMetrics` at `0x180015db5`
- `USER32!GetSystemMetrics` at `0x180015dc2`
- `USER32!GetSystemMetrics` at `0x180015db5`
- `USER32!GetSystemMetrics` at `0x180015dc2`

## pseudocode

```c

```
