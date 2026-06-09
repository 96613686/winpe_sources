# SetEditInPlaceSize

- ea: `0x180078110`
- end: `0x1800783ea`
- name: `SetEditInPlaceSize`
- size: `730`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, LPRECT lprcDst@<rdx>, HGDIOBJ h@<r8>, int, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180077fa4`
- `0x180138e9c`

## callees

- `0x180016c78`
- `0x180078110`
- `0x180114520`

## import_xrefs

- `GDI32!SelectObject` at `0x1800781c1`
- `GDI32!SelectObject` at `0x1800781c1`
- `USER32!AdjustWindowRectEx` at `0x18007833f`
- `USER32!AdjustWindowRectEx` at `0x18007833f`
- `USER32!DrawTextW` at `0x180078238`
- `USER32!DrawTextW` at `0x180078238`
- `USER32!ShowCaret` at `0x1800783ba`
- `USER32!ShowCaret` at `0x1800783ba`
- `USER32!HideCaret` at `0x180078361`
- `USER32!HideCaret` at `0x180078361`
- `USER32!OffsetRect` at `0x180078296`
- `USER32!OffsetRect` at `0x180078296`
- `USER32!CopyRect` at `0x1800783a2`
- `USER32!CopyRect` at `0x1800783a2`
- `USER32!IntersectRect` at `0x1800782f0`
- `USER32!IntersectRect` at `0x1800782f0`
- `USER32!SetWindowPos` at `0x180078394`
- `USER32!SetWindowPos` at `0x180078394`
- `USER32!GetParent` at `0x180078168`
- `USER32!GetParent` at `0x180078168`
- `USER32!GetWindowTextW` at `0x180078183`
- `USER32!GetWindowTextW` at `0x180078183`
- `USER32!GetWindowLongW` at `0x18007831c`
- `USER32!GetWindowLongW` at `0x18007832c`
- `USER32!GetWindowLongW` at `0x18007831c`
- `USER32!GetWindowLongW` at `0x18007832c`
- `USER32!InflateRect` at `0x180078358`
- `USER32!InflateRect` at `0x180078358`
- `USER32!GetDC` at `0x1800781b2`
- `USER32!GetDC` at `0x1800781b2`
- `USER32!SendMessageW` at `0x180078306`
- `USER32!SendMessageW` at `0x180078306`
- `USER32!GetSystemMetrics` at `0x1800781e6`
- `USER32!GetSystemMetrics` at `0x1800782a3`
- `USER32!GetSystemMetrics` at `0x1800782b9`
- `USER32!GetSystemMetrics` at `0x1800781e6`
- `USER32!GetSystemMetrics` at `0x1800782a3`
- `USER32!GetSystemMetrics` at `0x1800782b9`
- `USER32!GetClientRect` at `0x1800782db`
- `USER32!GetClientRect` at `0x1800782db`
- `USER32!InvalidateRect` at `0x1800783b1`
- `USER32!InvalidateRect` at `0x1800783b1`
- `USER32!ReleaseDC` at `0x1800782cb`
- `USER32!ReleaseDC` at `0x1800782cb`
- `USER32!GetSystemMetricsForDpi` at `0x1800781d9`
- `USER32!GetSystemMetricsForDpi` at `0x1800781d9`

## pseudocode

```c

```
