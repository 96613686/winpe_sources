# CLink::Paint(HDC__ *,tagRECT const *,tagRECT const *)

- ea: `0x1800f175c`
- end: `0x1800f18bf`
- name: `?Paint@CLink@@AEAAXPEAUHDC__@@PEBUtagRECT@@1@Z`
- size: `355`
- prototype: `void(CLink *__hidden this, HDC, const struct tagRECT *, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180076850`

## callees

- `0x1800f175c`
- `0x180114520`
- `0x1801d1010`

## import_xrefs

- `GDI32!SetBkMode` at `0x1800f1837`
- `GDI32!SetBkMode` at `0x1800f1837`
- `GDI32!SelectObject` at `0x1800f1811`
- `GDI32!SelectObject` at `0x1800f1882`
- `GDI32!SelectObject` at `0x1800f1811`
- `GDI32!SelectObject` at `0x1800f1882`
- `USER32!FillRect` at `0x1800f1857`
- `USER32!FillRect` at `0x1800f1857`
- `USER32!GetParent` at `0x1800f17e9`
- `USER32!GetParent` at `0x1800f17e9`
- `USER32!GetDC` at `0x1800f17cd`
- `USER32!GetDC` at `0x1800f17cd`
- `USER32!SendMessageW` at `0x1800f17fd`
- `USER32!SendMessageW` at `0x1800f17fd`
- `USER32!GetClientRect` at `0x1800f179d`
- `USER32!GetClientRect` at `0x1800f179d`
- `USER32!ReleaseDC` at `0x1800f1899`
- `USER32!ReleaseDC` at `0x1800f1899`
- `UxTheme!DrawThemeParentBackground` at `0x1800f1848`
- `UxTheme!DrawThemeParentBackground` at `0x1800f1848`

## pseudocode

```c

```
