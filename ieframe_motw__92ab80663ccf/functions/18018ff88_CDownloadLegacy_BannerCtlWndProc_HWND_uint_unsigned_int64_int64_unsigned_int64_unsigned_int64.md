# CDownloadLegacy::_BannerCtlWndProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)

- ea: `0x18018ff88`
- end: `0x1801902cc`
- name: `?_BannerCtlWndProc@CDownloadLegacy@@IEAA_JPEAUHWND__@@I_K_J11@Z`
- size: `836`
- prototype: `__int64(CDownloadLegacy *__hidden this, HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1801920f0`

## callees

- `0x1800975f0`
- `0x18018ff88`
- `0x180591ef6`
- `0x180591f80`

## import_xrefs

- `msvcrt!_wtoi` at `0x18019013a`
- `msvcrt!_wtoi` at `0x18019013a`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18019009e`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180190126`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18019009e`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180190126`
- `GDI32!DeleteObject` at `0x1801901f6`
- `GDI32!DeleteObject` at `0x1801901f6`
- `GDI32!SelectObject` at `0x18019016c`
- `GDI32!SelectObject` at `0x1801901e2`
- `GDI32!SelectObject` at `0x18019016c`
- `GDI32!SelectObject` at `0x1801901e2`
- `GDI32!GetObjectW` at `0x1801900ff`
- `GDI32!GetObjectW` at `0x1801900ff`
- `GDI32!CreateFontIndirectW` at `0x180190157`
- `GDI32!CreateFontIndirectW` at `0x180190157`
- `GDI32!SetTextColor` at `0x180190181`
- `GDI32!SetTextColor` at `0x180190181`
- `GDI32!SetBkMode` at `0x180190195`
- `GDI32!SetBkMode` at `0x180190195`
- `GDI32!TextOutW` at `0x1801901cb`
- `GDI32!TextOutW` at `0x1801901cb`
- `USER32!DestroyIcon` at `0x180190286`
- `USER32!DestroyIcon` at `0x180190286`
- `USER32!GetSysColor` at `0x180190079`
- `USER32!GetSysColor` at `0x180190079`
- `USER32!DrawIconEx` at `0x180190277`
- `USER32!DrawIconEx` at `0x180190277`
- `USER32!ReleaseDC` at `0x180190299`
- `USER32!ReleaseDC` at `0x180190299`
- `USER32!GetDC` at `0x18018ffec`
- `USER32!GetDC` at `0x18018ffec`
- `USER32!SendDlgItemMessageW` at `0x1801900c7`
- `USER32!SendDlgItemMessageW` at `0x1801900c7`
- `USER32!LoadImageW` at `0x18019022a`
- `USER32!LoadImageW` at `0x18019022a`
- `USER32!DefWindowProcW` at `0x18018ffd0`
- `USER32!DefWindowProcW` at `0x18018ffd0`
- `MSIMG32!GradientFill` at `0x180190060`
- `MSIMG32!GradientFill` at `0x180190060`

## pseudocode

```c

```
