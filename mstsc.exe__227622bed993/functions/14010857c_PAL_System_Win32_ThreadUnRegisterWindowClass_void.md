# PAL_System_Win32_ThreadUnRegisterWindowClass(void)

- ea: `0x14010857c`
- end: `0x1401087cc`
- name: `?PAL_System_Win32_ThreadUnRegisterWindowClass@@YAJXZ`
- size: `592`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1401093dc`

## callees

- `0x140001010`
- `0x140001b00`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14010857c`
- `0x1401091c0`
- `0x140111220`

## import_xrefs

- `USER32!UnregisterClassW` at `0x1401086e8`
- `USER32!UnregisterClassW` at `0x1401086e8`
- `KERNEL32!GetLastError` at `0x140108690`
- `KERNEL32!GetLastError` at `0x1401086f6`
- `KERNEL32!GetLastError` at `0x140108690`
- `KERNEL32!GetLastError` at `0x1401086f6`
- `KERNEL32!GetModuleHandleExW` at `0x140108686`
- `KERNEL32!GetModuleHandleExW` at `0x140108686`

## string_xrefs

- `0x140108735`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x14010871e`: `PAL_System_Win32_ThreadUnRegisterWindowClass`
- `0x1401085ca`: `Thread window class not registered. Skipping unregister.`

## pseudocode

```c

```
