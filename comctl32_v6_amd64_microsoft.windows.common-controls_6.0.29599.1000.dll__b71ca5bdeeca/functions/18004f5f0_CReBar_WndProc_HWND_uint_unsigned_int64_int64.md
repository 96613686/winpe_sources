# CReBar::_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18004f5f0`
- end: `0x180050a40`
- name: `?_WndProc@CReBar@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `5200`
- prototype: `__int64 __fastcall(CReBar *__hidden this, HWND hWnd, UINT Msg, unsigned int, LPARAM lParam)`
- caller_count: `1`
- callee_count: `68`
- tags: `authz_impersonation`

## callers

- `0x18004f4e0`

## callees

- `0x180005b30`
- `0x180011f44`
- `0x180022bec`
- `0x180022f08`
- `0x180026340`
- `0x18002639c`
- `0x180036850`
- `0x18003fe20`
- `0x18004b888`
- `0x18004ba00`
- `0x18004c95c`
- `0x18004d1dc`
- `0x18004df60`
- `0x18004e018`
- `0x18004e7dc`
- `0x18004eb3c`
- `0x18004ef28`
- `0x18004f3bc`
- `0x18004f420`
- `0x18004f5f0`
- `0x180050a48`
- `0x180050f38`
- `0x1800518dc`
- `0x180051dfc`
- `0x1800527d4`
- `0x180052c38`
- `0x180052de8`
- `0x180052e70`
- `0x180052f1c`
- `0x1800534f8`
- `0x1800537b4`
- `0x1800538ac`
- `0x1800539a4`
- `0x180053c04`
- `0x1800553b4`
- `0x18006a640`
- `0x18006ea30`
- `0x1800d4364`
- `0x1800d7820`
- `0x1800d958c`
- `0x1800d9628`
- `0x1800db5f8`
- `0x1800df43c`
- `0x1800e1528`
- `0x1800e52b0`
- `0x1800e5d90`
- `0x1800e7d90`
- `0x1800e85a0`
- `0x1800e8680`
- `0x1800ed458`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fff7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005006a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fff7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005006a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050078`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050078`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18005005f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18005005f`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18004fd23`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18004fd23`
- `USER32!GetWindowDC` at `0x18004f951`
- `USER32!GetWindowDC` at `0x18004f951`
- `USER32!OffsetRect` at `0x18004f948`
- `USER32!OffsetRect` at `0x18004f948`
- `USER32!SetWindowPos` at `0x1800506d3`
- `USER32!SetWindowPos` at `0x1800506d3`
- `USER32!SetCapture` at `0x18004fc07`
- `USER32!SetCapture` at `0x18004fc07`
- `USER32!DefWindowProcW` at `0x18004f76a`
- `USER32!DefWindowProcW` at `0x18004f8db`
- `USER32!DefWindowProcW` at `0x18005026d`
- `USER32!DefWindowProcW` at `0x18004f76a`
- `USER32!DefWindowProcW` at `0x18004f8db`
- `USER32!DefWindowProcW` at `0x18005026d`
- `USER32!GetWindowRect` at `0x18004f92f`
- `USER32!GetWindowRect` at `0x18004f92f`
- `USER32!InflateRect` at `0x18004fa2a`
- `USER32!InflateRect` at `0x18004fa2a`
- `USER32!ScreenToClient` at `0x18004fd79`
- `USER32!ScreenToClient` at `0x18004fd79`
- `USER32!SendMessageW` at `0x18004fadf`
- `USER32!SendMessageW` at `0x18004fd3f`
- `USER32!SendMessageW` at `0x18004ff1f`
- `USER32!SendMessageW` at `0x180050109`
- `USER32!SendMessageW` at `0x1800502ce`
- `USER32!SendMessageW` at `0x18004fadf`
- `USER32!SendMessageW` at `0x18004fd3f`
- `USER32!SendMessageW` at `0x18004ff1f`
- `USER32!SendMessageW` at `0x180050109`
- `USER32!SendMessageW` at `0x1800502ce`
- `USER32!GetSystemMetrics` at `0x18004fa0b`
- `USER32!GetSystemMetrics` at `0x18004fa1a`
- `USER32!GetSystemMetrics` at `0x18004fa0b`
- `USER32!GetSystemMetrics` at `0x18004fa1a`
- `USER32!GetWindowLongPtrW` at `0x18004fca9`
- `USER32!GetWindowLongPtrW` at `0x18004fca9`
- `USER32!InvalidateRect` at `0x18004ffd3`
- `USER32!InvalidateRect` at `0x180050120`
- `USER32!InvalidateRect` at `0x180050306`
- `USER32!InvalidateRect` at `0x1800506a2`
- `USER32!InvalidateRect` at `0x18004ffd3`
- `USER32!InvalidateRect` at `0x180050120`
- `USER32!InvalidateRect` at `0x180050306`
- `USER32!InvalidateRect` at `0x1800506a2`
- `USER32!ReleaseDC` at `0x18004f98e`
- `USER32!ReleaseDC` at `0x18004f98e`
- `USER32!PostMessageW` at `0x1800500e2`
- `USER32!PostMessageW` at `0x1800500e2`
- `USER32!CreateWindowExW` at `0x18004fd0e`
- `USER32!CreateWindowExW` at `0x18004fd0e`
- `UxTheme!SetWindowTheme` at `0x18004fe1e`
- `UxTheme!SetWindowTheme` at `0x18004fe1e`
- `OLEACC!LresultFromObject` at `0x18004fee6`
- `OLEACC!LresultFromObject` at `0x18004fee6`

## pseudocode

```c

```
