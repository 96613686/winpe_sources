# PaintWithPaletteBitmap(HDC__ *,PROPDATA const *,tagRECT const *,HPALETTE__ *,HBITMAP__ *)

- ea: `0x1801223a0`
- end: `0x180122542`
- name: `?PaintWithPaletteBitmap@@YAXPEAUHDC__@@PEBUPROPDATA@@PEBUtagRECT@@PEAUHPALETTE__@@PEAUHBITMAP__@@@Z`
- size: `418`
- prototype: `void __usercall(HDC hdcDest@<rcx>, const struct PROPDATA *@<rdx>, const struct tagRECT *@<r8>, HPALETTE@<r9>, HBITMAP)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180122738`
- `0x180122974`

## callees

- `0x180114520`
- `0x1801223a0`

## import_xrefs

- `GDI32!GetObjectW` at `0x1801223ef`
- `GDI32!GetObjectW` at `0x1801223ef`
- `GDI32!SelectObject` at `0x180122407`
- `GDI32!SelectObject` at `0x180122407`
- `GDI32!DeleteDC` at `0x18012251a`
- `GDI32!DeleteDC` at `0x18012251a`
- `GDI32!CreateCompatibleDC` at `0x1801223f8`
- `GDI32!CreateCompatibleDC` at `0x1801223f8`
- `GDI32!BitBlt` at `0x18012247f`
- `GDI32!BitBlt` at `0x18012247f`
- `GDI32!SelectPalette` at `0x18012241b`
- `GDI32!SelectPalette` at `0x18012241b`
- `GDI32!RealizePalette` at `0x180122424`
- `GDI32!RealizePalette` at `0x180122424`
- `GDI32!StretchBlt` at `0x1801224cb`
- `GDI32!StretchBlt` at `0x180122511`
- `GDI32!StretchBlt` at `0x1801224cb`
- `GDI32!StretchBlt` at `0x180122511`

## pseudocode

```c

```
