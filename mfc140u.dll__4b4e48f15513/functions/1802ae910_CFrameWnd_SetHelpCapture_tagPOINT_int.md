# CFrameWnd::SetHelpCapture(tagPOINT,int *)

- ea: `0x1802ae910`
- end: `0x1802aea62`
- name: `?SetHelpCapture@CFrameWnd@@IEAAPEAUHWND__@@UtagPOINT@@PEAH@Z`
- size: `338`
- prototype: `HWND__ *__fastcall(CFrameWnd *this, tagPOINT point, int *pbDescendant)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1802ae6a0`
- `0x1802aea70`

## callees

- `0x180296d00`
- `0x18029a470`
- `0x1802a9c20`
- `0x1802ae910`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1802ae995`
- `KERNEL32!GetCurrentThreadId` at `0x1802ae995`
- `USER32!GetActiveWindow` at `0x1802ae979`
- `USER32!GetActiveWindow` at `0x1802ae979`
- `USER32!GetWindowThreadProcessId` at `0x1802ae9a8`
- `USER32!GetWindowThreadProcessId` at `0x1802ae9a8`
- `USER32!GetCapture` at `0x1802ae945`
- `USER32!GetCapture` at `0x1802ae945`
- `USER32!GetDesktopWindow` at `0x1802ae9b9`
- `USER32!GetDesktopWindow` at `0x1802ae9b9`
- `USER32!SetCursor` at `0x1802aea34`
- `USER32!SetCursor` at `0x1802aea34`
- `USER32!WindowFromPoint` at `0x1802ae951`
- `USER32!WindowFromPoint` at `0x1802ae951`
- `USER32!SetCapture` at `0x1802ae9f8`
- `USER32!SetCapture` at `0x1802ae9f8`
- `USER32!ReleaseCapture` at `0x1802aea19`
- `USER32!ReleaseCapture` at `0x1802aea27`
- `USER32!ReleaseCapture` at `0x1802aea19`
- `USER32!ReleaseCapture` at `0x1802aea27`

## pseudocode

```c

```
