# PAL_System_Win32_ThreadUnRegisterWindowClass(void)

- ea: `0x14010a6ec`
- end: `0x14010a93c`
- name: `?PAL_System_Win32_ThreadUnRegisterWindowClass@@YAJXZ`
- size: `592`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14010b54c`

## callees

- `0x140001010`
- `0x140001b00`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14010a6ec`
- `0x14010b330`
- `0x140113390`

## import_xrefs

- `USER32!UnregisterClassW` at `0x14010a858`
- `USER32!UnregisterClassW` at `0x14010a858`
- `KERNEL32!GetLastError` at `0x14010a800`
- `KERNEL32!GetLastError` at `0x14010a866`
- `KERNEL32!GetLastError` at `0x14010a800`
- `KERNEL32!GetLastError` at `0x14010a866`
- `KERNEL32!GetModuleHandleExW` at `0x14010a7f6`
- `KERNEL32!GetModuleHandleExW` at `0x14010a7f6`

## string_xrefs

- `0x14010a8a5`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x14010a88e`: `PAL_System_Win32_ThreadUnRegisterWindowClass`
- `0x14010a73a`: `Thread window class not registered. Skipping unregister.`

## pseudocode

```c

```
