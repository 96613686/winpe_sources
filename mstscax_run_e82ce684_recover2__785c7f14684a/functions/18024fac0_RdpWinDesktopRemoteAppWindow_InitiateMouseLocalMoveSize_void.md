# RdpWinDesktopRemoteAppWindow::InitiateMouseLocalMoveSize(void)

- ea: `0x18024fac0`
- end: `0x180250148`
- name: `?InitiateMouseLocalMoveSize@RdpWinDesktopRemoteAppWindow@@IEAAJXZ`
- size: `1672`
- prototype: `__int64 __fastcall(RdpWinDesktopRemoteAppWindow *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting`

## callers

- `0x1802519a8`

## callees

- `0x1800011f4`
- `0x180002ebc`
- `0x180003554`
- `0x18000376c`
- `0x18001f5d0`
- `0x180039ce4`
- `0x180082910`
- `0x180082ad8`
- `0x1800e9b1c`
- `0x1800f1b88`
- `0x1800f63b8`
- `0x18024fac0`
- `0x1802509c8`
- `0x180256adc`
- `0x180257aac`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180250051`
- `KERNEL32!GetLastError` at `0x180250051`
- `KERNEL32!MulDiv` at `0x18025000a`
- `KERNEL32!MulDiv` at `0x18025001a`
- `KERNEL32!MulDiv` at `0x18025000a`
- `KERNEL32!MulDiv` at `0x18025001a`
- `USER32!GetCapture` at `0x18024ffe4`
- `USER32!GetCapture` at `0x18024ffe4`
- `USER32!SetCursorPos` at `0x18024fdf6`
- `USER32!SetCursorPos` at `0x180250110`
- `USER32!SetCursorPos` at `0x18024fdf6`
- `USER32!SetCursorPos` at `0x180250110`
- `USER32!GetCursorPos` at `0x18024fc25`
- `USER32!GetCursorPos` at `0x18024fc25`
- `USER32!GetAsyncKeyState` at `0x18024ff5b`
- `USER32!GetAsyncKeyState` at `0x18024ff5b`
- `USER32!GetWindowRect` at `0x18024fc3b`
- `USER32!GetWindowRect` at `0x18024fc3b`
- `USER32!SetTimer` at `0x1802500eb`
- `USER32!SetTimer` at `0x1802500eb`
- `USER32!ReleaseCapture` at `0x18024ffef`
- `USER32!ReleaseCapture` at `0x18024ffef`
- `USER32!SendInput` at `0x180250041`
- `USER32!SendInput` at `0x180250041`

## string_xrefs

- `0x18025008e`: `clientcore\termsrv\rdp\win\remoteapp\remoteappplugin\implementation\rdpwin32remoteappwindow.cpp`
- `0x18024fbe8`: `Initial cursor for move size start, from server`
- `0x18024fb06`: `Initiating mouse based movesize`
- `0x18024fe51`: `InitiateMouseLocalMoveSize()`
- `0x18024fe10`: `InitiateMouseLocalMoveSize`
- `0x180250075`: `InitiateMouseLocalMoveSize`
- `0x18024fd4d`: `Modified cursor for move size start`
- `0x18025009c`: `Failed SendInput. Aborting local move.`
- `0x18024ffa9`: `Mouse button is still down. Procedding with local move/size`
- `0x18024ff75`: `Mouse button is already up. Not doing local move/size`
- `0x18024fefa`: `Starting local move/size on client.`

## pseudocode

```c

```
