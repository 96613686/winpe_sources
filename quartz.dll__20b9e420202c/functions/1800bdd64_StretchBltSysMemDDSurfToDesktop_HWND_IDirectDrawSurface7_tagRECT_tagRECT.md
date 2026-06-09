# StretchBltSysMemDDSurfToDesktop(HWND__ *,IDirectDrawSurface7 *,tagRECT *,tagRECT *)

- ea: `0x1800bdd64`
- end: `0x1800bdf2f`
- name: `?StretchBltSysMemDDSurfToDesktop@@YAJPEAUHWND__@@PEAUIDirectDrawSurface7@@PEAUtagRECT@@2@Z`
- size: `459`
- prototype: `__int64 __fastcall(HWND hWnd, struct IDirectDrawSurface7 *, struct tagRECT *, struct tagRECT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800bba94`

## callees

- `0x1800bdd64`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800bdece`
- `KERNEL32!GetLastError` at `0x1800bdece`
- `GDI32!SetStretchBltMode` at `0x1800bde22`
- `GDI32!SetStretchBltMode` at `0x1800bde38`
- `GDI32!SetStretchBltMode` at `0x1800bde22`
- `GDI32!SetStretchBltMode` at `0x1800bde38`
- `GDI32!StretchBlt` at `0x1800bdebe`
- `GDI32!StretchBlt` at `0x1800bdebe`
- `USER32!MapWindowPoints` at `0x1800bde52`
- `USER32!MapWindowPoints` at `0x1800bde52`
- `USER32!ReleaseDC` at `0x1800bdef1`
- `USER32!ReleaseDC` at `0x18015c9dc`
- `USER32!ReleaseDC` at `0x1800bdef1`
- `USER32!ReleaseDC` at `0x18015c9dc`
- `USER32!GetDC` at `0x1800bddc8`
- `USER32!GetDC` at `0x1800bddc8`
- `USER32!IsRectEmpty` at `0x1800bdd97`
- `USER32!IsRectEmpty` at `0x1800bdd97`

## pseudocode

```c

```
