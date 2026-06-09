# COSKKeyboardManager::WinEventProc(HWINEVENTHOOK__ *,ulong,HWND__ *,long,long,ulong,ulong)

- ea: `0x140013e50`
- end: `0x140013ea3`
- name: `?WinEventProc@COSKKeyboardManager@@SAXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@Z`
- size: `83`
- prototype: `void __stdcall(HWINEVENTHOOK hWinEventHook, DWORD event, HWND hwnd, LONG idObject, LONG idChild, DWORD idEventThread, DWORD dwmsEventTime)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000fb04`
- `0x140013e50`

## import_xrefs

- `USER32!SetTimer` at `0x140013e8f`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140013e74`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140013e74`

## pseudocode

```c

```
