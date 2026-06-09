# CDragOperation::PumpUIMessagesWhileWaitingForThread(void *)

- ea: `0x1800949e4`
- end: `0x180094abf`
- name: `?PumpUIMessagesWhileWaitingForThread@CDragOperation@@QEAAXPEAX@Z`
- size: `219`
- prototype: `void __fastcall(CDragOperation *this, void *threadHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180040754`

## callees

- `0x1800949e4`

## import_xrefs

- `USER32!PostQuitMessage` at `0x180094a8a`
- `USER32!PostQuitMessage` at `0x180094a8a`
- `USER32!SetCursor` at `0x180094a7f`
- `USER32!SetCursor` at `0x180094a7f`
- `USER32!LoadCursorW` at `0x180094a76`
- `USER32!LoadCursorW` at `0x180094a76`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180094aab`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180094aab`
- `USER32!CallMsgFilterW` at `0x180094a38`
- `USER32!CallMsgFilterW` at `0x180094a38`
- `USER32!PeekMessageW` at `0x180094a22`
- `USER32!PeekMessageW` at `0x180094a22`
- `USER32!TranslateMessage` at `0x180094a46`
- `USER32!TranslateMessage` at `0x180094a58`
- `USER32!TranslateMessage` at `0x180094a46`
- `USER32!TranslateMessage` at `0x180094a58`
- `USER32!DispatchMessageW` at `0x180094a50`
- `USER32!DispatchMessageW` at `0x180094a50`

## pseudocode

```c

```
