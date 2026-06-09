# CHidPairing::s_DeviceNotificationWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800b2930`
- end: `0x1800b2a16`
- name: `?s_DeviceNotificationWndProc@CHidPairing@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `230`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000ac48`
- `0x1800b0d84`
- `0x1800b2930`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800b29b3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800b29b3`
- `USER32!GetWindowLongPtrW` at `0x1800b294a`
- `USER32!GetWindowLongPtrW` at `0x1800b294a`
- `USER32!DefWindowProcW` at `0x1800b2a03`
- `USER32!DefWindowProcW` at `0x1800b2a03`
- `USER32!PostQuitMessage` at `0x1800b29f2`
- `USER32!PostQuitMessage` at `0x1800b29f2`

## string_xrefs

- `0x1800b2989`: `CHidPairing::s_DeviceNotificationWndProc - Failed to install device.`

## pseudocode

```c

```
