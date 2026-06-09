# CContextMenuOverExplorerCommands::InsertMenuItemForSubCommands(HMENU__ *,uint,uint,uint,ulong,ushort const *)

- ea: `0x18001d574`
- end: `0x18001d718`
- name: `?InsertMenuItemForSubCommands@CContextMenuOverExplorerCommands@@AEAA_NPEAUHMENU__@@IIIKPEBG@Z`
- size: `420`
- prototype: `bool(CContextMenuOverExplorerCommands *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014920`

## callees

- `0x18001d574`
- `0x180026394`
- `0x180073d68`
- `0x180078010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x18001d5ab`
- `SHCORE!IUnknown_SetSite` at `0x18001d6de`
- `SHCORE!IUnknown_SetSite` at `0x18001d5ab`
- `SHCORE!IUnknown_SetSite` at `0x18001d6de`
- `USER32!InsertMenuW` at `0x18001d660`
- `USER32!InsertMenuW` at `0x18001d660`
- `USER32!DestroyMenu` at `0x18001d6d2`
- `USER32!DestroyMenu` at `0x18001d6d2`
- `USER32!CreatePopupMenu` at `0x18001d634`
- `USER32!CreatePopupMenu` at `0x18001d634`
- `USER32!InsertMenuItemW` at `0x18001d6bc`
- `USER32!InsertMenuItemW` at `0x18001d6bc`

## pseudocode

```c

```
