# CHTMLPopup::CalcValidPopupRect(tagRECT &,CDoc *,bool,bool)

- ea: `0x1809e9480`
- end: `0x1809e991a`
- name: `?CalcValidPopupRect@CHTMLPopup@@AEBAIAEAUtagRECT@@PEAVCDoc@@_N2@Z`
- size: `1178`
- prototype: `unsigned int __usercall@<eax>(CHTMLPopup *__hidden this@<rcx>, struct tagRECT *@<rdx>, struct CDoc *@<r8>, bool@<r9b>, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1809ead40`
- `0x1809eb728`

## callees

- `0x1803e7198`
- `0x180402d68`
- `0x18072f374`
- `0x18084df8c`
- `0x1809e9480`
- `0x1809ea370`
- `0x1810f6516`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1809e95c6`
- `KERNEL32!CompareStringW` at `0x1809e95c6`
- `USER32!GetParent` at `0x1809e95e9`
- `USER32!GetParent` at `0x1809e95e9`
- `USER32!GetWindowThreadProcessId` at `0x1809e950d`
- `USER32!GetWindowThreadProcessId` at `0x1809e95fd`
- `USER32!GetWindowThreadProcessId` at `0x1809e950d`
- `USER32!GetWindowThreadProcessId` at `0x1809e95fd`
- `USER32!GetClassNameW` at `0x1809e9538`
- `USER32!GetClassNameW` at `0x1809e9538`
- `USER32!GetDesktopWindow` at `0x1809e9820`
- `USER32!GetDesktopWindow` at `0x1809e9820`
- `USER32!GetWindowRect` at `0x1809e9622`
- `USER32!GetWindowRect` at `0x1809e9834`
- `USER32!GetWindowRect` at `0x1809e9622`
- `USER32!GetWindowRect` at `0x1809e9834`
- `USER32!IntersectRect` at `0x1809e963d`
- `USER32!IntersectRect` at `0x1809e963d`
- `USER32!GetMonitorInfoW` at `0x1809e9800`
- `USER32!GetMonitorInfoW` at `0x1809e9800`
- `USER32!MonitorFromPoint` at `0x1809e97cb`
- `USER32!MonitorFromPoint` at `0x1809e97cb`

## pseudocode

```c

```
