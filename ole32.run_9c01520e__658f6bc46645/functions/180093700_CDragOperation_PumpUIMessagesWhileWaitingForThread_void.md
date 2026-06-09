# CDragOperation::PumpUIMessagesWhileWaitingForThread(void *)

- ea: `0x180093700`
- end: `0x180093819`
- name: `?PumpUIMessagesWhileWaitingForThread@CDragOperation@@QEAAXPEAX@Z`
- size: `281`
- prototype: `void __fastcall(CDragOperation *this, void *threadHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180042474`

## callees

- `0x180093700`

## import_xrefs

- `USER32!PostQuitMessage` at `0x1800937d7`
- `USER32!PostQuitMessage` at `0x1800937d7`
- `USER32!SetCursor` at `0x1800937c3`
- `USER32!SetCursor` at `0x1800937c3`
- `USER32!LoadCursorW` at `0x1800937b4`
- `USER32!LoadCursorW` at `0x1800937b4`
- `USER32!DispatchMessageW` at `0x180093782`
- `USER32!DispatchMessageW` at `0x180093782`
- `USER32!TranslateMessage` at `0x180093772`
- `USER32!TranslateMessage` at `0x180093790`
- `USER32!TranslateMessage` at `0x180093772`
- `USER32!TranslateMessage` at `0x180093790`
- `USER32!PeekMessageW` at `0x18009373e`
- `USER32!PeekMessageW` at `0x18009373e`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x1800937fe`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x1800937fe`
- `USER32!CallMsgFilterW` at `0x18009375e`
- `USER32!CallMsgFilterW` at `0x18009375e`

## pseudocode

```c

```
