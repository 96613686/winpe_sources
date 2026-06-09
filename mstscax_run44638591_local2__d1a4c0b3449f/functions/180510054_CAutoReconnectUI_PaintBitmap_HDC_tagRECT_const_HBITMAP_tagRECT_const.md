# CAutoReconnectUI::PaintBitmap(HDC__ *,tagRECT const *,HBITMAP__ *,tagRECT const *)

- ea: `0x180510054`
- end: `0x180510299`
- name: `?PaintBitmap@CAutoReconnectUI@@IEAAXPEAUHDC__@@PEBUtagRECT@@PEAUHBITMAP__@@1@Z`
- size: `581`
- prototype: `void(CAutoReconnectUI *__hidden this, HDC, const struct tagRECT *, HBITMAP, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18050fa3c`

## callees

- `0x18002a334`
- `0x180039ce4`
- `0x180510054`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `GDI32!SetStretchBltMode` at `0x180510184`
- `GDI32!SetStretchBltMode` at `0x180510258`
- `GDI32!SetStretchBltMode` at `0x180510184`
- `GDI32!SetStretchBltMode` at `0x180510258`
- `GDI32!StretchBlt` at `0x1805101e6`
- `GDI32!StretchBlt` at `0x1805101e6`
- `GDI32!DeleteDC` at `0x18051026f`
- `GDI32!DeleteDC` at `0x18051026f`
- `GDI32!SelectObject` at `0x180510139`
- `GDI32!SelectObject` at `0x180510266`
- `GDI32!SelectObject` at `0x180510139`
- `GDI32!SelectObject` at `0x180510266`
- `GDI32!CreateCompatibleDC` at `0x180510092`
- `GDI32!CreateCompatibleDC` at `0x180510092`
- `GDI32!GetObjectW` at `0x1805100dd`
- `GDI32!GetObjectW` at `0x1805100dd`
- `USER32!SetRect` at `0x180510125`
- `USER32!SetRect` at `0x180510125`

## pseudocode

```c

```
