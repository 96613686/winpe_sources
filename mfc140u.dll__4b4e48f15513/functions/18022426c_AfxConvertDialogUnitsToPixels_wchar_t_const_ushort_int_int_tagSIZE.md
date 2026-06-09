# _AfxConvertDialogUnitsToPixels(wchar_t const *,ushort,int,int,tagSIZE *)

- ea: `0x18022426c`
- end: `0x18022441c`
- name: `?_AfxConvertDialogUnitsToPixels@@YAXPEB_WGHHPEAUtagSIZE@@@Z`
- size: `432`
- prototype: `void __fastcall(const wchar_t *pszFontFace, unsigned __int16 wFontSize, int cxDlg, int cyDlg, tagSIZE *pSizePixel)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180224cb0`

## callees

- `0x18022426c`
- `0x180231d10`
- `0x180231d70`
- `0x1802c4640`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1802242d9`
- `KERNEL32!MulDiv` at `0x1802243ce`
- `KERNEL32!MulDiv` at `0x1802243e5`
- `KERNEL32!MulDiv` at `0x1802242d9`
- `KERNEL32!MulDiv` at `0x1802243ce`
- `KERNEL32!MulDiv` at `0x1802243e5`
- `VCRUNTIME140!memset` at `0x1802242bb`
- `VCRUNTIME140!memset` at `0x1802242bb`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180224302`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180224302`
- `USER32!GetDC` at `0x1802242a7`
- `USER32!GetDC` at `0x1802242a7`
- `USER32!ReleaseDC` at `0x1802243bd`
- `USER32!ReleaseDC` at `0x1802243bd`
- `USER32!GetDialogBaseUnits` at `0x1802243a1`
- `USER32!GetDialogBaseUnits` at `0x1802243aa`
- `USER32!GetDialogBaseUnits` at `0x1802243a1`
- `USER32!GetDialogBaseUnits` at `0x1802243aa`
- `GDI32!GetDeviceCaps` at `0x1802242c9`
- `GDI32!GetDeviceCaps` at `0x1802242c9`
- `GDI32!CreateFontIndirectW` at `0x180224323`
- `GDI32!CreateFontIndirectW` at `0x180224323`
- `GDI32!DeleteObject` at `0x180224399`
- `GDI32!DeleteObject` at `0x180224399`
- `GDI32!SelectObject` at `0x180224337`
- `GDI32!SelectObject` at `0x180224390`
- `GDI32!SelectObject` at `0x180224337`
- `GDI32!SelectObject` at `0x180224390`
- `GDI32!GetTextExtentPoint32W` at `0x18022436a`
- `GDI32!GetTextExtentPoint32W` at `0x18022436a`
- `GDI32!GetTextMetricsW` at `0x180224347`
- `GDI32!GetTextMetricsW` at `0x180224347`

## pseudocode

```c

```
