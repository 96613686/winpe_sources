# CicBridge::WinEventProc(HWINEVENTHOOK__ *,ulong,HWND__ *,long,long,ulong,ulong)

- ea: `0x180044590`
- end: `0x180044794`
- name: `?WinEventProc@CicBridge@@CAXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@Z`
- size: `516`
- prototype: `void __stdcall(HWINEVENTHOOK hWinEventHook, DWORD event, HWND hwnd, LONG idObject, LONG idChild, DWORD idEventThread, DWORD dwmsEventTime)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800139a4`
- `0x1800139c0`
- `0x18001cc80`
- `0x180044590`
- `0x180045040`
- `0x18010a010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x180044694`
- `ntdll!RtlDllShutdownInProgress` at `0x180044694`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800446d2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800446d2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800445b0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800445b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800446b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800446b7`
- `USER32!IsChild` at `0x180044622`
- `USER32!IsChild` at `0x180044622`
- `USER32!UnhookWinEvent` at `0x18004473d`
- `USER32!UnhookWinEvent` at `0x18004473d`

## pseudocode

```c

```
