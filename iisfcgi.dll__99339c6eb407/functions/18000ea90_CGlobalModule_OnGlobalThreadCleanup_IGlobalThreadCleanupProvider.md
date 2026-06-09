# CGlobalModule::OnGlobalThreadCleanup(IGlobalThreadCleanupProvider *)

- ea: `0x18000ea90`
- end: `0x18000eac8`
- name: `?OnGlobalThreadCleanup@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalThreadCleanupProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000eabb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000eabb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ea9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000eaa8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000eab5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ea9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000eaa8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000eab5`

## string_xrefs

- `0x18000eaa1`: `CGlobalModule::OnGlobalThreadCleanup`

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
0x18000ea90  sub     rsp, 28h
0x18000ea94  lea     rcx, OutputString; "This module subscribed to event "
0x18000ea9b  call    cs:__imp_OutputDebugStringA
0x18000eaa1  lea     rcx, aCglobalmoduleO_0; "CGlobalModule::OnGlobalThreadCleanup"
0x18000eaa8  call    cs:__imp_OutputDebugStringA
0x18000eaae  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x18000eab5  call    cs:__imp_OutputDebugStringA
0x18000eabb  call    cs:__imp_DebugBreak
0x18000eac1  xor     eax, eax
0x18000eac3  add     rsp, 28h
0x18000eac7  retn
```
