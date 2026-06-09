# CPreviewDC::ComputeDeltas(int &,wchar_t const *,uint &,int,uint,int *,int,wchar_t *,int *,int &)

- ea: `0x1802109a0`
- end: `0x180210d05`
- name: `?ComputeDeltas@CPreviewDC@@IEAA?AVCSize@@AEAHPEB_WAEAIHIPEAHHPEA_W30@Z`
- size: `869`
- prototype: `CSize *__fastcall(CPreviewDC *this, CSize *result, int *x, const wchar_t *lpszString, unsigned int *nCount, int bTabbed, unsigned int nTabStops, int *lpnTabStops, int nTabOrigin, wchar_t *lpszOutputString, int *pnDxWidths, int *nRightFixup)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180210d50`
- `0x180210ee0`

## callees

- `0x1802109a0`
- `0x180231d70`
- `0x1802c4640`

## import_xrefs

- `USER32!GetTabbedTextExtentW` at `0x180210acd`
- `USER32!GetTabbedTextExtentW` at `0x180210acd`
- `GDI32!GetCharWidthW` at `0x180210b31`
- `GDI32!GetCharWidthW` at `0x180210b4b`
- `GDI32!GetCharWidthW` at `0x180210b31`
- `GDI32!GetCharWidthW` at `0x180210b4b`
- `GDI32!GetTextExtentPoint32W` at `0x180210a3f`
- `GDI32!GetTextExtentPoint32W` at `0x180210bcd`
- `GDI32!GetTextExtentPoint32W` at `0x180210a3f`
- `GDI32!GetTextExtentPoint32W` at `0x180210bcd`
- `GDI32!GetTextMetricsW` at `0x180210a13`
- `GDI32!GetTextMetricsW` at `0x180210a21`
- `GDI32!GetTextMetricsW` at `0x180210a13`
- `GDI32!GetTextMetricsW` at `0x180210a21`
- `GDI32!GetTextAlign` at `0x180210a4e`
- `GDI32!GetTextAlign` at `0x180210a4e`
- `GDI32!GetCurrentPositionEx` at `0x180210a69`
- `GDI32!GetCurrentPositionEx` at `0x180210a69`
- `GDI32!MoveToEx` at `0x180210cc6`
- `GDI32!MoveToEx` at `0x180210cc6`

## pseudocode

```c

```
