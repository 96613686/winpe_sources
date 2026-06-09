# CDeviceUpdates::CreateMsgWindow(void)

- ea: `0x180571948`
- end: `0x180571bb7`
- name: `?CreateMsgWindow@CDeviceUpdates@@AEAAJXZ`
- size: `623`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180572370`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x180571948`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x18057198b`
- `KERNEL32!GetModuleHandleExW` at `0x18057198b`
- `KERNEL32!GetLastError` at `0x18057199c`
- `KERNEL32!GetLastError` at `0x180571a79`
- `KERNEL32!GetLastError` at `0x180571b0f`
- `KERNEL32!GetLastError` at `0x18057199c`
- `KERNEL32!GetLastError` at `0x180571a79`
- `KERNEL32!GetLastError` at `0x180571b0f`
- `USER32!SetWindowLongPtrW` at `0x180571ad0`
- `USER32!SetWindowLongPtrW` at `0x180571ad0`
- `USER32!DestroyWindow` at `0x180571b8e`
- `USER32!DestroyWindow` at `0x180571b8e`
- `USER32!RegisterClassW` at `0x180571a15`
- `USER32!RegisterClassW` at `0x180571a15`
- `USER32!RegisterDeviceNotificationW` at `0x180571afc`
- `USER32!RegisterDeviceNotificationW` at `0x180571afc`
- `USER32!UnregisterDeviceNotification` at `0x180571b77`
- `USER32!UnregisterDeviceNotification` at `0x180571b77`
- `USER32!CreateWindowExW` at `0x180571a6a`
- `USER32!CreateWindowExW` at `0x180571a6a`

## string_xrefs

- `0x1805719fe`: `DeviceUpdateClass`

## pseudocode

```c

```
