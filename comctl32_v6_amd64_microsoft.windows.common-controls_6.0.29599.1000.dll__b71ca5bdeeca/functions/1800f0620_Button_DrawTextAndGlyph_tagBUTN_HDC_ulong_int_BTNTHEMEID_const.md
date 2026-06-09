# Button_DrawTextAndGlyph(tagBUTN *,HDC__ *,ulong,int,BTNTHEMEID const &)

- ea: `0x1800f0620`
- end: `0x1800f0db5`
- name: `?Button_DrawTextAndGlyph@@YAXPEAUtagBUTN@@PEAUHDC__@@KHAEBUBTNTHEMEID@@@Z`
- size: `1941`
- prototype: `void __usercall(struct tagBUTN *@<rcx>, HDC hdc@<rdx>, unsigned int@<r8d>, int@<r9d>, const struct BTNTHEMEID *)`
- caller_count: `4`
- callee_count: `13`
- tags: ``

## callers

- `0x1800af320`
- `0x1800afcdc`
- `0x1800f5400`
- `0x18013a1c0`

## callees

- `0x18006a640`
- `0x180075ab0`
- `0x1800add20`
- `0x1800ae5b4`
- `0x1800af658`
- `0x1800af9d0`
- `0x1800afbd4`
- `0x1800f0620`
- `0x1800f533c`
- `0x180114520`
- `0x18013a428`
- `0x18013a5d8`
- `0x18013ad00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f06d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f093c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f0983`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f0d7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f06d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f093c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f0983`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f0d7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f0991`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f0d88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f0991`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f0d88`
- `GDI32!GetTextExtentPoint32W` at `0x1800f097d`
- `GDI32!GetTextExtentPoint32W` at `0x1800f09a6`
- `GDI32!GetTextExtentPoint32W` at `0x1800f097d`
- `GDI32!GetTextExtentPoint32W` at `0x1800f09a6`
- `GDI32!IntersectClipRect` at `0x1800f07ed`
- `GDI32!IntersectClipRect` at `0x1800f07ed`
- `GDI32!SetBkColor` at `0x1800f0803`
- `GDI32!SetBkColor` at `0x1800f0803`
- `GDI32!SetBkMode` at `0x1800f0b99`
- `GDI32!SetBkMode` at `0x1800f0b99`
- `GDI32!SetTextColor` at `0x1800f0819`
- `GDI32!SetTextColor` at `0x1800f0b5c`
- `GDI32!SetTextColor` at `0x1800f0819`
- `GDI32!SetTextColor` at `0x1800f0b5c`
- `GDI32!GetBkColor` at `0x1800f0b35`
- `GDI32!GetBkColor` at `0x1800f0b35`
- `USER32!CopyRect` at `0x1800f0c49`
- `USER32!CopyRect` at `0x1800f0c49`
- `USER32!DrawFocusRect` at `0x1800f0d74`
- `USER32!DrawFocusRect` at `0x1800f0d74`
- `USER32!GetSysColorBrush` at `0x1800f0849`
- `USER32!GetSysColorBrush` at `0x1800f0b82`
- `USER32!GetSysColorBrush` at `0x1800f0849`
- `USER32!GetSysColorBrush` at `0x1800f0b82`
- `USER32!IsWindowEnabled` at `0x1800f0b15`
- `USER32!IsWindowEnabled` at `0x1800f0b15`
- `USER32!GetWindowTextW` at `0x1800f075e`
- `USER32!GetWindowTextW` at `0x1800f075e`
- `USER32!InflateRect` at `0x1800f0d67`
- `USER32!InflateRect` at `0x1800f0d67`
- `USER32!GetSystemMetrics` at `0x1800f067f`
- `USER32!GetSystemMetrics` at `0x1800f068e`
- `USER32!GetSystemMetrics` at `0x1800f069d`
- `USER32!GetSystemMetrics` at `0x1800f06ab`
- `USER32!GetSystemMetrics` at `0x1800f0a21`
- `USER32!GetSystemMetrics` at `0x1800f0a36`
- `USER32!GetSystemMetrics` at `0x1800f0b22`
- `USER32!GetSystemMetrics` at `0x1800f067f`
- `USER32!GetSystemMetrics` at `0x1800f068e`
- `USER32!GetSystemMetrics` at `0x1800f069d`
- `USER32!GetSystemMetrics` at `0x1800f06ab`
- `USER32!GetSystemMetrics` at `0x1800f0a21`
- `USER32!GetSystemMetrics` at `0x1800f0a36`
- `USER32!GetSystemMetrics` at `0x1800f0b22`
- `USER32!GetSysColor` at `0x1800f07f8`
- `USER32!GetSysColor` at `0x1800f080e`
- `USER32!GetSysColor` at `0x1800f0b42`
- `USER32!GetSysColor` at `0x1800f0b51`
- `USER32!GetSysColor` at `0x1800f07f8`
- `USER32!GetSysColor` at `0x1800f080e`
- `USER32!GetSysColor` at `0x1800f0b42`
- `USER32!GetSysColor` at `0x1800f0b51`
- `USER32!GetClientRect` at `0x1800f0c34`
- `USER32!GetClientRect` at `0x1800f0c34`
- `USER32!SetRect` at `0x1800f0a8f`
- `USER32!SetRect` at `0x1800f0a8f`
- `USER32!GetWindowTextLengthW` at `0x1800f06c6`
- `USER32!GetWindowTextLengthW` at `0x1800f06c6`
- `USER32!DrawStateW` at `0x1800f0bd7`
- `USER32!DrawStateW` at `0x1800f0bd7`
- `UxTheme!GetThemeTextExtent` at `0x1800f0cc6`
- `UxTheme!GetThemeTextExtent` at `0x1800f0cc6`
- `UxTheme!GetThemeBackgroundContentRect` at `0x1800f0c84`
- `UxTheme!GetThemeBackgroundContentRect` at `0x1800f0c84`

## pseudocode

```c

```
