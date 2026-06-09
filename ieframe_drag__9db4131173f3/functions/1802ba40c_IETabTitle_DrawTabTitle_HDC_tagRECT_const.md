# IETabTitle::_DrawTabTitle(HDC__ *,tagRECT const *)

- ea: `0x1802ba40c`
- end: `0x1802ba84e`
- name: `?_DrawTabTitle@IETabTitle@@AEAAJPEAUHDC__@@PEBUtagRECT@@@Z`
- size: `1090`
- prototype: `__int64 __fastcall(IETabTitle *__hidden this, HDC hdc, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1802b6dd0`

## callees

- `0x18000f470`
- `0x18001ecf8`
- `0x18001efd8`
- `0x180086510`
- `0x1800904f4`
- `0x180093ec0`
- `0x1800b10f0`
- `0x1802b47e0`
- `0x1802b4814`
- `0x1802b4848`
- `0x1802b48b8`
- `0x1802b48ec`
- `0x1802ba40c`
- `0x180410c18`
- `0x180449aa8`
- `0x18054e286`
- `0x18054e2da`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1802ba58b`
- `KERNEL32!TlsGetValue` at `0x1802ba58b`
- `GDI32!CreateDIBSection` at `0x1802ba502`
- `GDI32!CreateDIBSection` at `0x1802ba502`
- `GDI32!DeleteObject` at `0x1802ba80d`
- `GDI32!DeleteObject` at `0x1802ba80d`
- `GDI32!SelectObject` at `0x1802ba572`
- `GDI32!SelectObject` at `0x1802ba623`
- `GDI32!SelectObject` at `0x1802ba7e0`
- `GDI32!SelectObject` at `0x1802ba804`
- `GDI32!SelectObject` at `0x1802ba572`
- `GDI32!SelectObject` at `0x1802ba623`
- `GDI32!SelectObject` at `0x1802ba7e0`
- `GDI32!SelectObject` at `0x1802ba804`
- `GDI32!DeleteDC` at `0x1802ba81f`
- `GDI32!DeleteDC` at `0x1802ba81f`
- `GDI32!CreateCompatibleDC` at `0x1802ba4a7`
- `GDI32!CreateCompatibleDC` at `0x1802ba4a7`
- `USER32!GetClientRect` at `0x1802ba49e`
- `USER32!GetClientRect` at `0x1802ba49e`
- `USER32!GetSysColor` at `0x1802ba67f`
- `USER32!GetSysColor` at `0x1802ba67f`
- `MSIMG32!AlphaBlend` at `0x1802ba7ca`
- `MSIMG32!AlphaBlend` at `0x1802ba7ca`
- `UxTheme!DrawThemeTextEx` at `0x1802ba6ce`
- `UxTheme!DrawThemeTextEx` at `0x1802ba6ce`
- `UxTheme!OpenThemeData` at `0x1802ba691`
- `UxTheme!OpenThemeData` at `0x1802ba691`

## pseudocode

```c

```
