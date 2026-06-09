# CFontCache::SetFaceNameFromGDI(uchar,char *,ulong)

- ea: `0x1800c7f44`
- end: `0x1800c8076`
- name: `?SetFaceNameFromGDI@CFontCache@@AEAAJEPEADK@Z`
- size: `306`
- prototype: `int(CFontCache *__hidden this, unsigned __int8, char *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800c81d4`

## callees

- `0x180012cd0`
- `0x1800c7f44`
- `0x1800cca00`

## import_xrefs

- `GDI32!EnumFontFamiliesExA` at `0x1800c8009`
- `GDI32!EnumFontFamiliesExA` at `0x1800c8009`
- `GDI32!GetObjectA` at `0x1800c7fc0`
- `GDI32!GetObjectA` at `0x1800c7fc0`
- `USER32!GetDC` at `0x1800c7fe4`
- `USER32!GetDC` at `0x1800c7fe4`
- `USER32!ReleaseDC` at `0x1800c8028`
- `USER32!ReleaseDC` at `0x1800c8028`

## pseudocode

```c

```
