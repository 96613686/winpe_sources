# CGlobalModule::OnGlobalThreadCleanup(IGlobalThreadCleanupProvider *)

- ea: `0x1800038c0`
- end: `0x1800038f8`
- name: `?OnGlobalThreadCleanup@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalThreadCleanupProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800038cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800038d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800038e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800038cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800038d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800038e5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800038eb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800038eb`

## string_xrefs

- `0x1800038d1`: `CGlobalModule::OnGlobalThreadCleanup`

## pseudocode

```c
__int64 CGlobalModule::OnGlobalThreadCleanup()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CGlobalModule::OnGlobalThreadCleanup");
  OutputDebugStringA(
    " but did not override the method in its CGlobalModule implementation.  Please check the method signature to make sur"
    "e it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800038c0  sub     rsp, 28h
0x1800038c4  lea     rcx, OutputString; "This module subscribed to event "
0x1800038cb  call    cs:__imp_OutputDebugStringA
0x1800038d1  lea     rcx, aCglobalmoduleO_0; "CGlobalModule::OnGlobalThreadCleanup"
0x1800038d8  call    cs:__imp_OutputDebugStringA
0x1800038de  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800038e5  call    cs:__imp_OutputDebugStringA
0x1800038eb  call    cs:__imp_DebugBreak
0x1800038f1  xor     eax, eax
0x1800038f3  add     rsp, 28h
0x1800038f7  retn
```
