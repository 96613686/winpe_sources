# Stream_WriteBitmap(IStream *,HBITMAP__ *,int)

- ea: `0x1800831e0`
- end: `0x1800834c9`
- name: `?Stream_WriteBitmap@@YAJPEAUIStream@@PEAUHBITMAP__@@H@Z`
- size: `745`
- prototype: `int(struct IStream *, HBITMAP, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800828e0`

## callees

- `0x1800115f0`
- `0x1800831e0`
- `0x18008ea60`
- `0x180090020`

## import_xrefs

- `GDI32!GetDIBits` at `0x18008330b`
- `GDI32!GetDIBits` at `0x180083435`
- `GDI32!GetDIBits` at `0x18008330b`
- `GDI32!GetDIBits` at `0x180083435`
- `GDI32!GetObjectW` at `0x18008325e`
- `GDI32!GetObjectW` at `0x18008325e`
- `KERNEL32!LocalFree` at `0x180083490`
- `KERNEL32!LocalFree` at `0x180083490`
- `KERNEL32!LocalAlloc` at `0x1800833d4`
- `KERNEL32!LocalAlloc` at `0x1800833d4`
- `USER32!GetDC` at `0x180083271`
- `USER32!GetDC` at `0x180083271`
- `USER32!ReleaseDC` at `0x180083482`
- `USER32!ReleaseDC` at `0x180083482`

## pseudocode

```c

```
