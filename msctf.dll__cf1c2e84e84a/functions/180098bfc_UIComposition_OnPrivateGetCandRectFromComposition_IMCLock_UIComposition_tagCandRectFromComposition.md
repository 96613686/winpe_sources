# UIComposition::OnPrivateGetCandRectFromComposition(IMCLock &,UIComposition::tagCandRectFromComposition *)

- ea: `0x180098bfc`
- end: `0x180098f72`
- name: `?OnPrivateGetCandRectFromComposition@UIComposition@@QEAAJAEAVIMCLock@@PEAUtagCandRectFromComposition@1@@Z`
- size: `886`
- prototype: `int(UIComposition *__hidden this, struct IMCLock *, struct UIComposition::tagCandRectFromComposition *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001a9e0`

## callees

- `0x1800185f0`
- `0x18001cc80`
- `0x180045520`
- `0x180045cd0`
- `0x180046db8`
- `0x180098bfc`

## import_xrefs

- `USER32!GetWindowRect` at `0x180098ce8`
- `USER32!GetWindowRect` at `0x180098ce8`
- `USER32!ClientToScreen` at `0x180098eff`
- `USER32!ClientToScreen` at `0x180098eff`
- `USER32!ReleaseDC` at `0x180098ccb`
- `USER32!ReleaseDC` at `0x180098e3b`
- `USER32!ReleaseDC` at `0x180098ccb`
- `USER32!ReleaseDC` at `0x180098e3b`
- `USER32!GetDC` at `0x180098c85`
- `USER32!GetDC` at `0x180098df4`
- `USER32!GetDC` at `0x180098c85`
- `USER32!GetDC` at `0x180098df4`
- `GDI32!SelectObject` at `0x180098c98`
- `GDI32!SelectObject` at `0x180098cbb`
- `GDI32!SelectObject` at `0x180098e07`
- `GDI32!SelectObject` at `0x180098e2b`
- `GDI32!SelectObject` at `0x180098c98`
- `GDI32!SelectObject` at `0x180098cbb`
- `GDI32!SelectObject` at `0x180098e07`
- `GDI32!SelectObject` at `0x180098e2b`
- `GDI32!GetTextExtentPoint32W` at `0x180098caf`
- `GDI32!GetTextExtentPoint32W` at `0x180098e1f`
- `GDI32!GetTextExtentPoint32W` at `0x180098caf`
- `GDI32!GetTextExtentPoint32W` at `0x180098e1f`

## string_xrefs

- `0x180098f3e`: `UIComposition::OnPrivateGetCandRectFromComposition. comp==NULL`

## pseudocode

```c

```
