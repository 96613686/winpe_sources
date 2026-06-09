# SysInfo::GetColorBitmap(HBITMAP__ * *)

- ea: `0x18002d04c`
- end: `0x18002d10a`
- name: `?GetColorBitmap@SysInfo@@QEAAJPEAPEAUHBITMAP__@@@Z`
- size: `190`
- prototype: `HRESULT __fastcall(SysInfo *this, HBITMAP__ **phbmpColor)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002aef4`
- `0x1800b89c8`

## callees

- `0x18002d04c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d0e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d0e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d6d33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d076`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d076`
- `GDI32!CreateCompatibleBitmap` at `0x18002d0ab`
- `GDI32!CreateCompatibleBitmap` at `0x18002d0ab`
- `USER32!ReleaseDC` at `0x18002d0c0`
- `USER32!ReleaseDC` at `0x18002d0c0`
- `USER32!GetDC` at `0x18002d08e`
- `USER32!GetDC` at `0x18002d08e`

## pseudocode

```c

```
