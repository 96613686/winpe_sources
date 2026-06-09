# CDownloadLegacy::_BannerCtlWndProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)

- ea: `0x18017da50`
- end: `0x18017dd17`
- name: `?_BannerCtlWndProc@CDownloadLegacy@@IEAA_JPEAUHWND__@@I_K_J11@Z`
- size: `711`
- prototype: `__int64(CDownloadLegacy *__hidden this, HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18017f850`

## callees

- `0x1800904f4`
- `0x18017da50`
- `0x18054e286`
- `0x18054e310`

## import_xrefs

- `msvcrt!_wtoi` at `0x18017dbce`
- `msvcrt!_wtoi` at `0x18017dbce`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18017db4e`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18017dbc0`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18017db4e`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18017dbc0`
- `GDI32!DeleteObject` at `0x18017dc60`
- `GDI32!DeleteObject` at `0x18017dc60`
- `GDI32!SelectObject` at `0x18017dbf4`
- `GDI32!SelectObject` at `0x18017dc52`
- `GDI32!SelectObject` at `0x18017dbf4`
- `GDI32!SelectObject` at `0x18017dc52`
- `GDI32!GetObjectW` at `0x18017db9f`
- `GDI32!GetObjectW` at `0x18017db9f`
- `GDI32!CreateFontIndirectW` at `0x18017dbe5`
- `GDI32!CreateFontIndirectW` at `0x18017dbe5`
- `GDI32!SetTextColor` at `0x18017dc03`
- `GDI32!SetTextColor` at `0x18017dc03`
- `GDI32!SetBkMode` at `0x18017dc11`
- `GDI32!SetBkMode` at `0x18017dc11`
- `GDI32!TextOutW` at `0x18017dc41`
- `GDI32!TextOutW` at `0x18017dc41`
- `USER32!DestroyIcon` at `0x18017dcde`
- `USER32!DestroyIcon` at `0x18017dcde`
- `USER32!GetSysColor` at `0x18017db2f`
- `USER32!GetSysColor` at `0x18017db2f`
- `USER32!DrawIconEx` at `0x18017dcd5`
- `USER32!DrawIconEx` at `0x18017dcd5`
- `USER32!ReleaseDC` at `0x18017dceb`
- `USER32!ReleaseDC` at `0x18017dceb`
- `USER32!GetDC` at `0x18017daae`
- `USER32!GetDC` at `0x18017daae`
- `USER32!SendDlgItemMessageW` at `0x18017db71`
- `USER32!SendDlgItemMessageW` at `0x18017db71`
- `USER32!LoadImageW` at `0x18017dc8e`
- `USER32!LoadImageW` at `0x18017dc8e`
- `USER32!DefWindowProcW` at `0x18017da98`
- `USER32!DefWindowProcW` at `0x18017da98`
- `MSIMG32!GradientFill` at `0x18017db1c`
- `MSIMG32!GradientFill` at `0x18017db1c`

## pseudocode

```c

```
