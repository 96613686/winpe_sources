# RdpWinDesktopRemoteAppWindow::UpdateWindowOnConnectionStateChanged(int)

- ea: `0x18025a8d4`
- end: `0x18025ae63`
- name: `?UpdateWindowOnConnectionStateChanged@RdpWinDesktopRemoteAppWindow@@QEAAXH@Z`
- size: `1423`
- prototype: `void __fastcall(RdpWinDesktopRemoteAppWindow *__hidden this, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update`

## callers

- `0x180251210`

## callees

- `0x180001e8c`
- `0x180002660`
- `0x180039ce4`
- `0x180091fc8`
- `0x1800e9b1c`
- `0x180241120`
- `0x18024df6c`
- `0x180250ec8`
- `0x18025205c`
- `0x18025649c`
- `0x1802575b4`
- `0x18025a8d4`
- `0x18025c624`
- `0x18025dcc0`
- `0x18025dda0`
- `0x180271d78`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x18025a95c`
- `USER32!GetWindowLongPtrW` at `0x18025a9b1`
- `USER32!GetWindowLongPtrW` at `0x18025a95c`
- `USER32!GetWindowLongPtrW` at `0x18025a9b1`
- `USER32!SetWindowLongPtrW` at `0x18025ac36`
- `USER32!SetWindowLongPtrW` at `0x18025ac4c`
- `USER32!SetWindowLongPtrW` at `0x18025ac59`
- `USER32!SetWindowLongPtrW` at `0x18025ac36`
- `USER32!SetWindowLongPtrW` at `0x18025ac4c`
- `USER32!SetWindowLongPtrW` at `0x18025ac59`
- `USER32!IsIconic` at `0x18025aa18`
- `USER32!IsIconic` at `0x18025aa18`
- `USER32!EnableWindow` at `0x18025aad7`
- `USER32!EnableWindow` at `0x18025aad7`
- `dwmapi!DwmGetWindowAttribute` at `0x18025adad`
- `dwmapi!DwmGetWindowAttribute` at `0x18025adad`

## string_xrefs

- `0x18025aa6d`: `clientcore\termsrv\rdp\win\remoteapp\remoteappplugin\implementation\rdpwin32remoteappwindow.cpp`
- `0x18025ab2d`: `clientcore\termsrv\rdp\win\remoteapp\remoteappplugin\implementation\rdpwin32remoteappwindow.cpp`
- `0x18025ab38`: `RemoveWindowSubclass failed`
- `0x18025a962`: `UpdateWindowOnConnectionStateChanged`
- `0x18025ab07`: `UpdateWindowOnConnectionStateChanged`
- `0x18025ad55`: `UpdateWindowStyle failed`

## pseudocode

```c

```
