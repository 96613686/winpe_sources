# CServer::OnNCLButtonDown(int,tagPOINTS,tagRECT *)

- ea: `0x1809cf374`
- end: `0x1809cf6b0`
- name: `?OnNCLButtonDown@CServer@@QEAAHHUtagPOINTS@@PEAUtagRECT@@@Z`
- size: `828`
- prototype: `__int64 __fastcall(CServer *__hidden this, int, struct tagPOINTS, struct tagRECT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180439d10`
- `0x1805657a4`

## callees

- `0x180560cd8`
- `0x180565e4c`
- `0x180732d44`
- `0x1809cf374`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `GDI32!IntersectClipRect` at `0x1809cf4d2`
- `GDI32!IntersectClipRect` at `0x1809cf4d2`
- `USER32!LockWindowUpdate` at `0x1809cf420`
- `USER32!LockWindowUpdate` at `0x1809cf685`
- `USER32!LockWindowUpdate` at `0x1809cf420`
- `USER32!LockWindowUpdate` at `0x1809cf685`
- `USER32!GetDCEx` at `0x1809cf4b4`
- `USER32!GetDCEx` at `0x1809cf4b4`
- `USER32!ReleaseDC` at `0x1809cf677`
- `USER32!ReleaseDC` at `0x1809cf677`
- `USER32!GetClientRect` at `0x1809cf472`
- `USER32!GetClientRect` at `0x1809cf472`
- `USER32!GetCapture` at `0x1809cf4fc`
- `USER32!GetCapture` at `0x1809cf4fc`
- `USER32!ReleaseCapture` at `0x1809cf67d`
- `USER32!ReleaseCapture` at `0x1809cf67d`
- `USER32!IntersectRect` at `0x1809cf484`
- `USER32!IntersectRect` at `0x1809cf484`
- `USER32!GetMessageW` at `0x1809cf4f6`
- `USER32!GetMessageW` at `0x1809cf4f6`
- `USER32!DispatchMessageW` at `0x1809cf64a`
- `USER32!DispatchMessageW` at `0x1809cf64a`
- `USER32!OffsetRect` at `0x1809cf45d`
- `USER32!OffsetRect` at `0x1809cf4a2`
- `USER32!OffsetRect` at `0x1809cf62f`
- `USER32!OffsetRect` at `0x1809cf45d`
- `USER32!OffsetRect` at `0x1809cf4a2`
- `USER32!OffsetRect` at `0x1809cf62f`
- `USER32!SetCapture` at `0x1809cf4e4`
- `USER32!SetCapture` at `0x1809cf4e4`

## pseudocode

```c

```
