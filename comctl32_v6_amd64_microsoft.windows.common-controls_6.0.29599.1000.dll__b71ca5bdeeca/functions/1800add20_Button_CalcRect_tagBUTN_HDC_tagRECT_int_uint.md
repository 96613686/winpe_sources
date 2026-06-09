# Button_CalcRect(tagBUTN *,HDC__ *,tagRECT *,int,uint)

- ea: `0x1800add20`
- end: `0x1800ae10f`
- name: `?Button_CalcRect@@YAXPEAUtagBUTN@@PEAUHDC__@@PEAUtagRECT@@HI@Z`
- size: `1007`
- prototype: `void __usercall(struct tagBUTN *@<rcx>, HDC hdc@<rdx>, LPRECT lprc@<r8>, int@<r9d>, unsigned int)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x1800dddb0`
- `0x1800ddf08`
- `0x1800f0620`
- `0x1800f5400`
- `0x18013a1c0`

## callees

- `0x18006a640`
- `0x1800add20`
- `0x1800ae5b4`
- `0x1800afa8c`
- `0x1800afae4`
- `0x1800f533c`
- `0x180114520`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ade75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800adfbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ade75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800adfbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800adfcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800adfcb`
- `GDI32!GetTextExtentPoint32W` at `0x1800ade50`
- `GDI32!GetTextExtentPoint32W` at `0x1800adec7`
- `GDI32!GetTextExtentPoint32W` at `0x1800ae094`
- `GDI32!GetTextExtentPoint32W` at `0x1800ade50`
- `GDI32!GetTextExtentPoint32W` at `0x1800adec7`
- `GDI32!GetTextExtentPoint32W` at `0x1800ae094`
- `USER32!SetRectEmpty` at `0x1800adfe2`
- `USER32!SetRectEmpty` at `0x1800adfe2`
- `USER32!GetWindowTextW` at `0x1800adea7`
- `USER32!GetWindowTextW` at `0x1800adea7`
- `USER32!InflateRect` at `0x1800ade11`
- `USER32!InflateRect` at `0x1800ade34`
- `USER32!InflateRect` at `0x1800ade11`
- `USER32!InflateRect` at `0x1800ade34`
- `USER32!GetSystemMetrics` at `0x1800add76`
- `USER32!GetSystemMetrics` at `0x1800add84`
- `USER32!GetSystemMetrics` at `0x1800add91`
- `USER32!GetSystemMetrics` at `0x1800add9f`
- `USER32!GetSystemMetrics` at `0x1800adf3a`
- `USER32!GetSystemMetrics` at `0x1800adf7b`
- `USER32!GetSystemMetrics` at `0x1800adf95`
- `USER32!GetSystemMetrics` at `0x1800adfac`
- `USER32!GetSystemMetrics` at `0x1800add76`
- `USER32!GetSystemMetrics` at `0x1800add84`
- `USER32!GetSystemMetrics` at `0x1800add91`
- `USER32!GetSystemMetrics` at `0x1800add9f`
- `USER32!GetSystemMetrics` at `0x1800adf3a`
- `USER32!GetSystemMetrics` at `0x1800adf7b`
- `USER32!GetSystemMetrics` at `0x1800adf95`
- `USER32!GetSystemMetrics` at `0x1800adfac`
- `USER32!GetClientRect` at `0x1800addad`
- `USER32!GetClientRect` at `0x1800addad`
- `USER32!GetWindowTextLengthW` at `0x1800ade6c`
- `USER32!GetWindowTextLengthW` at `0x1800ade6c`
- `UxTheme!GetThemeTextExtent` at `0x1800adf1d`
- `UxTheme!GetThemeTextExtent` at `0x1800adf1d`

## pseudocode

```c

```
