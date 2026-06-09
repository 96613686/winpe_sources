# CUIGetIconBitmaps(HICON__ *,HBITMAP__ * *,HBITMAP__ * *,tagSIZE *)

- ea: `0x1800d9b54`
- end: `0x1800d9d20`
- name: `?CUIGetIconBitmaps@@YAHPEAUHICON__@@PEAPEAUHBITMAP__@@1PEAUtagSIZE@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(HICON, HBITMAP *, HBITMAP *, struct tagSIZE *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800dc160`
- `0x1800dc250`

## callees

- `0x180067794`
- `0x1800b8924`
- `0x1800d9b54`
- `0x1800d9d28`
- `0x1800da950`
- `0x180106a60`

## import_xrefs

- `USER32!DrawIconEx` at `0x1800d9c7a`
- `USER32!DrawIconEx` at `0x1800d9cb1`
- `USER32!DrawIconEx` at `0x1800d9c7a`
- `USER32!DrawIconEx` at `0x1800d9cb1`
- `USER32!FillRect` at `0x1800d9c40`
- `USER32!FillRect` at `0x1800d9c40`
- `GDI32!SelectObject` at `0x1800d9c07`
- `GDI32!SelectObject` at `0x1800d9c07`
- `GDI32!CreateBitmap` at `0x1800d9bf2`
- `GDI32!CreateBitmap` at `0x1800d9bf2`
- `GDI32!GetStockObject` at `0x1800d9c27`
- `GDI32!GetStockObject` at `0x1800d9c27`

## pseudocode

```c

```
