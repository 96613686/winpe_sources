# CToolbar::DrawButton(HDC__ *,int,int,_TBBUTTONDATA *,int,CTBHotState const &)

- ea: `0x180017808`
- end: `0x180018b81`
- name: `?DrawButton@CToolbar@@AEAAXPEAUHDC__@@HHPEAU_TBBUTTONDATA@@HAEBUCTBHotState@@@Z`
- size: `4985`
- prototype: `void __fastcall(CToolbar *__hidden this, HDC, int xLeft, int yTop, struct _TBBUTTONDATA *, int, const struct CTBHotState *)`
- caller_count: `4`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180017364`
- `0x1800eff34`
- `0x1800f3bb4`
- `0x180143560`

## callees

- `0x180017030`
- `0x180017808`
- `0x180018b88`
- `0x180018ed0`
- `0x180018fc4`
- `0x180019080`
- `0x1800190a0`
- `0x180036850`
- `0x1800a99c4`
- `0x1800b0910`
- `0x1800b0c4c`
- `0x1800b0c88`
- `0x1800be380`
- `0x1800ede24`
- `0x1800ee970`
- `0x180108b70`
- `0x180114520`
- `0x180114ebc`
- `0x1801266b0`
- `0x180126814`

## import_xrefs

- `GDI32!SetBkColor` at `0x180017f1b`
- `GDI32!SetBkColor` at `0x1800188c6`
- `GDI32!SetBkColor` at `0x18001891a`
- `GDI32!SetBkColor` at `0x180017f1b`
- `GDI32!SetBkColor` at `0x1800188c6`
- `GDI32!SetBkColor` at `0x18001891a`
- `GDI32!SetTextColor` at `0x180017c65`
- `GDI32!SetTextColor` at `0x180017e03`
- `GDI32!SetTextColor` at `0x180017f0d`
- `GDI32!SetTextColor` at `0x1800182f4`
- `GDI32!SetTextColor` at `0x1800188b8`
- `GDI32!SetTextColor` at `0x18001890e`
- `GDI32!SetTextColor` at `0x180017c65`
- `GDI32!SetTextColor` at `0x180017e03`
- `GDI32!SetTextColor` at `0x180017f0d`
- `GDI32!SetTextColor` at `0x1800182f4`
- `GDI32!SetTextColor` at `0x1800188b8`
- `GDI32!SetTextColor` at `0x18001890e`
- `GDI32!PatBlt` at `0x1800188f7`
- `GDI32!PatBlt` at `0x1800188f7`
- `GDI32!SelectObject` at `0x180017c55`
- `GDI32!SelectObject` at `0x180017e17`
- `GDI32!SelectObject` at `0x180017e2b`
- `GDI32!SelectObject` at `0x180017f8a`
- `GDI32!SelectObject` at `0x180017fdd`
- `GDI32!SelectObject` at `0x180017ffd`
- `GDI32!SelectObject` at `0x1800182e8`
- `GDI32!SelectObject` at `0x1800185ce`
- `GDI32!SelectObject` at `0x180018630`
- `GDI32!SelectObject` at `0x1800188a4`
- `GDI32!SelectObject` at `0x180018903`
- `GDI32!SelectObject` at `0x180017c55`
- `GDI32!SelectObject` at `0x180017e17`
- `GDI32!SelectObject` at `0x180017e2b`
- `GDI32!SelectObject` at `0x180017f8a`
- `GDI32!SelectObject` at `0x180017fdd`
- `GDI32!SelectObject` at `0x180017ffd`
- `GDI32!SelectObject` at `0x1800182e8`
- `GDI32!SelectObject` at `0x1800185ce`
- `GDI32!SelectObject` at `0x180018630`
- `GDI32!SelectObject` at `0x1800188a4`
- `GDI32!SelectObject` at `0x180018903`
- `GDI32!CreateCompatibleDC` at `0x180017de8`
- `GDI32!CreateCompatibleDC` at `0x180017de8`
- `GDI32!SetLayout` at `0x1800186e5`
- `GDI32!SetLayout` at `0x1800186e5`
- `GDI32!BitBlt` at `0x180017fd1`
- `GDI32!BitBlt` at `0x180018624`
- `GDI32!BitBlt` at `0x180018a0e`
- `GDI32!BitBlt` at `0x180017fd1`
- `GDI32!BitBlt` at `0x180018624`
- `GDI32!BitBlt` at `0x180018a0e`
- `GDI32!GetStockObject` at `0x18001792d`
- `GDI32!GetStockObject` at `0x18001793c`
- `GDI32!GetStockObject` at `0x18001792d`
- `GDI32!GetStockObject` at `0x18001793c`
- `GDI32!GetLayout` at `0x180017e37`
- `GDI32!GetLayout` at `0x1800186ce`
- `GDI32!GetLayout` at `0x180017e37`
- `GDI32!GetLayout` at `0x1800186ce`
- `USER32!GetKeyState` at `0x180017a21`
- `USER32!GetKeyState` at `0x180018177`
- `USER32!GetKeyState` at `0x180017a21`
- `USER32!GetKeyState` at `0x180018177`
- `USER32!GetSysColorBrush` at `0x180017f7e`
- `USER32!GetSysColorBrush` at `0x1800185c2`
- `USER32!GetSysColorBrush` at `0x180017f7e`
- `USER32!GetSysColorBrush` at `0x1800185c2`
- `USER32!GetCapture` at `0x1800184aa`
- `USER32!GetCapture` at `0x1800185a1`
- `USER32!GetCapture` at `0x1800184aa`
- `USER32!GetCapture` at `0x1800185a1`
- `USER32!GetSystemMetrics` at `0x1800178f2`
- `USER32!GetSystemMetrics` at `0x180018665`
- `USER32!GetSystemMetrics` at `0x18001867c`
- `USER32!GetSystemMetrics` at `0x1800187a5`
- `USER32!GetSystemMetrics` at `0x180018825`
- `USER32!GetSystemMetrics` at `0x180018833`
- `USER32!GetSystemMetrics` at `0x1800189d3`
- `USER32!GetSystemMetrics` at `0x1800178f2`
- `USER32!GetSystemMetrics` at `0x180018665`
- `USER32!GetSystemMetrics` at `0x18001867c`
- `USER32!GetSystemMetrics` at `0x1800187a5`
- `USER32!GetSystemMetrics` at `0x180018825`
- `USER32!GetSystemMetrics` at `0x180018833`
- `USER32!GetSystemMetrics` at `0x1800189d3`
- `USER32!GetSysColor` at `0x18001794b`
- `USER32!GetSysColor` at `0x180017959`
- `USER32!GetSysColor` at `0x180017967`
- `USER32!GetSysColor` at `0x180017975`
- `USER32!GetSysColor` at `0x180017991`
- `USER32!GetSysColor` at `0x18001794b`
- `USER32!GetSysColor` at `0x180017959`
- `USER32!GetSysColor` at `0x180017967`
- `USER32!GetSysColor` at `0x180017975`
- `USER32!GetSysColor` at `0x180017991`
- `USER32!SetRect` at `0x1800178d5`
- `USER32!SetRect` at `0x1800179aa`
- `USER32!SetRect` at `0x1800178d5`
- `USER32!SetRect` at `0x1800179aa`
- `UxTheme!DrawThemeBackground` at `0x180017ea5`
- `UxTheme!DrawThemeBackground` at `0x1800182d5`
- `UxTheme!DrawThemeBackground` at `0x180017ea5`
- `UxTheme!DrawThemeBackground` at `0x1800182d5`
- `UxTheme!GetThemeBool` at `0x180017f63`
- `UxTheme!GetThemeBool` at `0x180017f63`
- `UxTheme!GetThemeBackgroundContentRect` at `0x180017be0`
- `UxTheme!GetThemeBackgroundContentRect` at `0x180018b52`
- `UxTheme!GetThemeBackgroundContentRect` at `0x180017be0`
- `UxTheme!GetThemeBackgroundContentRect` at `0x180018b52`
- `UxTheme!GetThemeColor` at `0x180018ac9`
- `UxTheme!GetThemeColor` at `0x180018ac9`

## pseudocode

```c

```
