# CMsiCustomActionManager::ShutdownEEUIServer(void)

- ea: `0x18020c1b4`
- end: `0x18020c2f5`
- name: `?ShutdownEEUIServer@CMsiCustomActionManager@@QEAAIXZ`
- size: `321`
- prototype: `unsigned int __fastcall(CMsiCustomActionManager *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180179c4c`
- `0x1801bac70`
- `0x1801cf360`

## callees

- `0x1800080a8`
- `0x18020c1b4`
- `0x180266010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18020c2c3`
- `KERNEL32!CloseHandle` at `0x18020c2c3`
- `KERNEL32!LeaveCriticalSection` at `0x18020c2dd`
- `KERNEL32!LeaveCriticalSection` at `0x18020c2dd`
- `KERNEL32!EnterCriticalSection` at `0x18020c1ca`
- `KERNEL32!EnterCriticalSection` at `0x18020c1ca`
- `USER32!MsgWaitForMultipleObjects` at `0x18020c2ac`
- `USER32!MsgWaitForMultipleObjects` at `0x18020c2ac`
- `USER32!PeekMessageW` at `0x18020c287`
- `USER32!PeekMessageW` at `0x18020c287`
- `USER32!TranslateMessage` at `0x18020c259`
- `USER32!TranslateMessage` at `0x18020c259`
- `USER32!DispatchMessageW` at `0x18020c26a`
- `USER32!DispatchMessageW` at `0x18020c26a`

## pseudocode

```c

```
