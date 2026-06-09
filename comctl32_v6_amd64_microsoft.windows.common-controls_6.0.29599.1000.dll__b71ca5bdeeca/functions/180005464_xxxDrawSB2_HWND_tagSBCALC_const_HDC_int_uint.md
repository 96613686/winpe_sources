# xxxDrawSB2(HWND__ *,tagSBCALC const *,HDC__ *,int,uint)

- ea: `0x180005464`
- end: `0x18000590b`
- name: `?xxxDrawSB2@@YAXPEAUHWND__@@PEBUtagSBCALC@@PEAUHDC__@@HI@Z`
- size: `1191`
- prototype: `void __usercall(HWND hWnd@<rcx>, const struct tagSBCALC *@<rdx>, HDC@<r8>, int@<r9d>, unsigned int)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x180002800`
- `0x1800036b0`
- `0x1800e3a20`

## callees

- `0x18000340c`
- `0x180004498`
- `0x180004528`
- `0x180004c74`
- `0x180004e7c`
- `0x180004e9c`
- `0x1800050fc`
- `0x180005464`
- `0x180005d8c`
- `0x1800b89ac`
- `0x180114520`

## import_xrefs

- `GDI32!SetBkColor` at `0x18000568c`
- `GDI32!SetBkColor` at `0x18000568c`
- `GDI32!SetTextColor` at `0x180005698`
- `GDI32!SetTextColor` at `0x180005698`
- `GDI32!SelectObject` at `0x1800055b9`
- `GDI32!SelectObject` at `0x180005680`
- `GDI32!SelectObject` at `0x1800055b9`
- `GDI32!SelectObject` at `0x180005680`
- `GDI32!GetBkColor` at `0x18000556f`
- `GDI32!GetBkColor` at `0x18000556f`
- `GDI32!GetTextColor` at `0x18000557b`
- `GDI32!GetTextColor` at `0x18000557b`
- `USER32!CopyRect` at `0x1800055cb`
- `USER32!CopyRect` at `0x1800055cb`
- `USER32!GetSysColorBrush` at `0x1800055ad`
- `USER32!GetSysColorBrush` at `0x1800055ad`
- `USER32!DefWindowProcW` at `0x1800055a2`
- `USER32!DefWindowProcW` at `0x1800055a2`
- `USER32!DrawFrameControl` at `0x180005868`
- `USER32!DrawFrameControl` at `0x1800058c6`
- `USER32!DrawFrameControl` at `0x180005900`
- `USER32!DrawFrameControl` at `0x180005868`
- `USER32!DrawFrameControl` at `0x1800058c6`
- `USER32!DrawFrameControl` at `0x180005900`
- `USER32!GetSystemMetricsForDpi` at `0x180005506`
- `USER32!GetSystemMetricsForDpi` at `0x180005506`
- `UxTheme!DrawThemeBackground` at `0x180005610`
- `UxTheme!DrawThemeBackground` at `0x180005650`
- `UxTheme!DrawThemeBackground` at `0x180005834`
- `UxTheme!DrawThemeBackground` at `0x180005610`
- `UxTheme!DrawThemeBackground` at `0x180005650`
- `UxTheme!DrawThemeBackground` at `0x180005834`

## pseudocode

```c

```
