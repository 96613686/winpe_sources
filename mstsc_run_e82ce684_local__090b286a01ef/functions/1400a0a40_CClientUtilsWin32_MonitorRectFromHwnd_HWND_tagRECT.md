# CClientUtilsWin32::MonitorRectFromHwnd(HWND__ *,tagRECT *)

- ea: `0x1400a0a40`
- end: `0x1400a0b13`
- name: `?MonitorRectFromHwnd@CClientUtilsWin32@@SAHPEAUHWND__@@PEAUtagRECT@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(HWND hwnd, LPRECT lprcDst)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400155ec`

## callees

- `0x1400a0a40`
- `0x140113390`

## import_xrefs

- `USER32!MonitorFromWindow` at `0x1400a0ac1`
- `USER32!MonitorFromWindow` at `0x1400a0ac1`
- `USER32!GetMonitorInfoW` at `0x1400a0ad4`
- `USER32!GetMonitorInfoW` at `0x1400a0ad4`
- `USER32!SetRect` at `0x1400a0aa6`
- `USER32!SetRect` at `0x1400a0aa6`
- `USER32!CopyRect` at `0x1400a0ae6`
- `USER32!CopyRect` at `0x1400a0ae6`
- `USER32!GetSystemMetrics` at `0x1400a0a87`
- `USER32!GetSystemMetrics` at `0x1400a0a91`
- `USER32!GetSystemMetrics` at `0x1400a0ab1`
- `USER32!GetSystemMetrics` at `0x1400a0a87`
- `USER32!GetSystemMetrics` at `0x1400a0a91`
- `USER32!GetSystemMetrics` at `0x1400a0ab1`

## pseudocode

```c

```
