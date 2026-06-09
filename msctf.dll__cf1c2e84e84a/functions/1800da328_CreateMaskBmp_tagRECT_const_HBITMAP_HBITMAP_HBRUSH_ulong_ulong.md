# CreateMaskBmp(tagRECT const *,HBITMAP__ *,HBITMAP__ *,HBRUSH__ *,ulong,ulong)

- ea: `0x1800da328`
- end: `0x1800da50e`
- name: `?CreateMaskBmp@@YAPEAUHBITMAP__@@PEBUtagRECT@@PEAU1@1PEAUHBRUSH__@@KK@Z`
- size: `486`
- prototype: `HBITMAP(const struct tagRECT *, HBITMAP, HBITMAP, HBRUSH, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1800db930`
- `0x1800dbbc0`
- `0x1800dcc50`
- `0x1801027ec`

## callees

- `0x180067794`
- `0x1800b8924`
- `0x1800da328`
- `0x1800da950`
- `0x1800dadac`
- `0x180106a60`

## import_xrefs

- `USER32!FillRect` at `0x1800da400`
- `USER32!FillRect` at `0x1800da400`
- `USER32!SetRect` at `0x1800da3b3`
- `USER32!SetRect` at `0x1800da3b3`
- `GDI32!SetBkColor` at `0x1800da3e5`
- `GDI32!SetBkColor` at `0x1800da426`
- `GDI32!SetBkColor` at `0x1800da3e5`
- `GDI32!SetBkColor` at `0x1800da426`
- `GDI32!SetTextColor` at `0x1800da3cb`
- `GDI32!SetTextColor` at `0x1800da413`
- `GDI32!SetTextColor` at `0x1800da3cb`
- `GDI32!SetTextColor` at `0x1800da413`
- `GDI32!BitBlt` at `0x1800da46b`
- `GDI32!BitBlt` at `0x1800da4b0`
- `GDI32!BitBlt` at `0x1800da46b`
- `GDI32!BitBlt` at `0x1800da4b0`

## pseudocode

```c

```
