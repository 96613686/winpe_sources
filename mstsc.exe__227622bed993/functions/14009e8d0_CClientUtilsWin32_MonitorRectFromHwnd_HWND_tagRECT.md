# CClientUtilsWin32::MonitorRectFromHwnd(HWND__ *,tagRECT *)

- ea: `0x14009e8d0`
- end: `0x14009e9a3`
- name: `?MonitorRectFromHwnd@CClientUtilsWin32@@SAHPEAUHWND__@@PEAUtagRECT@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(HWND hwnd, LPRECT lprcDst)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400155ec`

## callees

- `0x14009e8d0`
- `0x140111220`

## import_xrefs

- `USER32!MonitorFromWindow` at `0x14009e951`
- `USER32!MonitorFromWindow` at `0x14009e951`
- `USER32!GetMonitorInfoW` at `0x14009e964`
- `USER32!GetMonitorInfoW` at `0x14009e964`
- `USER32!SetRect` at `0x14009e936`
- `USER32!SetRect` at `0x14009e936`
- `USER32!CopyRect` at `0x14009e976`
- `USER32!CopyRect` at `0x14009e976`
- `USER32!GetSystemMetrics` at `0x14009e917`
- `USER32!GetSystemMetrics` at `0x14009e921`
- `USER32!GetSystemMetrics` at `0x14009e941`
- `USER32!GetSystemMetrics` at `0x14009e917`
- `USER32!GetSystemMetrics` at `0x14009e921`
- `USER32!GetSystemMetrics` at `0x14009e941`

## pseudocode

```c

```
