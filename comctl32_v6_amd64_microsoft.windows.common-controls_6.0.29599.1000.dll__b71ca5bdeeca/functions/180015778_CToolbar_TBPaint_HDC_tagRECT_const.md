# CToolbar::TBPaint(HDC__ *,tagRECT const &)

- ea: `0x180015778`
- end: `0x180015aa6`
- name: `?TBPaint@CToolbar@@AEAAXPEAUHDC__@@AEBUtagRECT@@@Z`
- size: `814`
- prototype: `void __fastcall(CToolbar *__hidden this, HDC, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800134f0`

## callees

- `0x180005224`
- `0x180015778`
- `0x180015eb8`
- `0x180016030`
- `0x1800a99c4`
- `0x180114520`

## import_xrefs

- `GDI32!GetDCDpiScaleValue` at `0x1800158ca`
- `GDI32!GetDCDpiScaleValue` at `0x1800158ca`
- `USER32!IsRectEmpty` at `0x1800157c8`
- `USER32!IsRectEmpty` at `0x1800157c8`
- `USER32!GetClientRect` at `0x1800157b5`
- `USER32!GetClientRect` at `0x1800157b5`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18001587a`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18001587a`
- `UxTheme!EndBufferedAnimation` at `0x18001594f`
- `UxTheme!EndBufferedAnimation` at `0x18001594f`
- `UxTheme!BeginBufferedAnimation` at `0x18001590a`
- `UxTheme!BeginBufferedAnimation` at `0x18001590a`
- `UxTheme!BufferedPaintRenderAnimation` at `0x1800157fe`
- `UxTheme!BufferedPaintRenderAnimation` at `0x1800157fe`
- `UxTheme!BufferedPaintInit` at `0x180015a56`
- `UxTheme!BufferedPaintInit` at `0x180015a56`
- `UxTheme!GetThemeTransitionDuration` at `0x1800159ee`
- `UxTheme!GetThemeTransitionDuration` at `0x1800159ee`

## pseudocode

```c

```
