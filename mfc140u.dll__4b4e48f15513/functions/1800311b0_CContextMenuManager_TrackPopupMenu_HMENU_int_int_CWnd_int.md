# CContextMenuManager::TrackPopupMenu(HMENU__ *,int,int,CWnd *,int)

- ea: `0x1800311b0`
- end: `0x180031563`
- name: `?TrackPopupMenu@CContextMenuManager@@UEAAIPEAUHMENU__@@HHPEAVCWnd@@H@Z`
- size: `947`
- prototype: `unsigned int __fastcall(CContextMenuManager *this, HMENU__ *hmenuPopup, int x, int y, CWnd *pWndOwner, int bRightAlign)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x1800311b0`
- `0x180041130`
- `0x1800bdd60`
- `0x180139860`
- `0x180139950`
- `0x18023f820`
- `0x180296d00`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180031546`
- `KERNEL32!GetCurrentThreadId` at `0x180031546`
- `USER32!PostThreadMessageW` at `0x18003155b`
- `USER32!PostThreadMessageW` at `0x18003155b`
- `USER32!GetWindowRect` at `0x180031258`
- `USER32!GetWindowRect` at `0x180031258`
- `USER32!IsWindow` at `0x18003137c`
- `USER32!IsWindow` at `0x1800313c9`
- `USER32!IsWindow` at `0x1800313e7`
- `USER32!IsWindow` at `0x180031424`
- `USER32!IsWindow` at `0x18003149f`
- `USER32!IsWindow` at `0x1800314b6`
- `USER32!IsWindow` at `0x18003137c`
- `USER32!IsWindow` at `0x1800313c9`
- `USER32!IsWindow` at `0x1800313e7`
- `USER32!IsWindow` at `0x180031424`
- `USER32!IsWindow` at `0x18003149f`
- `USER32!IsWindow` at `0x1800314b6`
- `USER32!WaitMessage` at `0x1800314ad`
- `USER32!WaitMessage` at `0x1800314ad`
- `USER32!DispatchMessageW` at `0x18003141b`
- `USER32!DispatchMessageW` at `0x18003141b`
- `USER32!TranslateMessage` at `0x180031411`
- `USER32!TranslateMessage` at `0x180031411`
- `USER32!PeekMessageW` at `0x180031473`
- `USER32!PeekMessageW` at `0x180031473`
- `USER32!PostMessageW` at `0x1800314f8`
- `USER32!PostMessageW` at `0x1800314f8`
- `USER32!GetParent` at `0x180031275`
- `USER32!GetParent` at `0x18003128c`
- `USER32!GetParent` at `0x1800312d7`
- `USER32!GetParent` at `0x1800312ee`
- `USER32!GetParent` at `0x180031275`
- `USER32!GetParent` at `0x18003128c`
- `USER32!GetParent` at `0x1800312d7`
- `USER32!GetParent` at `0x1800312ee`

## pseudocode

```c

```
