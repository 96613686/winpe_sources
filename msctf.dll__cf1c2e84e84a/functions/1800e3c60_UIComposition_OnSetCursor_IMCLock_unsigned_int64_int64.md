# UIComposition::OnSetCursor(IMCLock &,unsigned __int64,__int64)

- ea: `0x1800e3c60`
- end: `0x1800e3d8c`
- name: `?OnSetCursor@UIComposition@@QEAAJAEAVIMCLock@@_K_J@Z`
- size: `300`
- prototype: `__int64 __fastcall(UIComposition *__hidden this, struct IMCLock *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180045950`

## callees

- `0x1800185f0`
- `0x18001cc80`
- `0x180045520`
- `0x180094ef4`
- `0x1800e3c60`
- `0x1800e4c60`

## import_xrefs

- `USER32!GetCursorPos` at `0x1800e3cdf`
- `USER32!GetCursorPos` at `0x1800e3cdf`
- `USER32!GetKeyState` at `0x1800e3d03`
- `USER32!GetKeyState` at `0x1800e3d14`
- `USER32!GetKeyState` at `0x1800e3d2a`
- `USER32!GetKeyState` at `0x1800e3d03`
- `USER32!GetKeyState` at `0x1800e3d14`
- `USER32!GetKeyState` at `0x1800e3d2a`

## string_xrefs

- `0x1800e3d61`: `UIComposition::OnSetCursor. imc_ctfime==NULL`
- `0x1800e3ccf`: `UIComposition::OnSetCursor. _pCicContext==NULL`

## pseudocode

```c

```
