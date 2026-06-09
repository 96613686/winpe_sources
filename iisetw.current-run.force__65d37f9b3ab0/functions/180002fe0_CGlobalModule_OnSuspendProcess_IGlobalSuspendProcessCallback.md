# CGlobalModule::OnSuspendProcess(IGlobalSuspendProcessCallback * *)

- ea: `0x180002fe0`
- end: `0x180003018`
- name: `?OnSuspendProcess@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAPEAVIGlobalSuspendProcessCallback@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002feb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ff8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003005`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002feb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ff8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003005`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000300b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000300b`

## pseudocode

```c
__int64 CGlobalModule::OnSuspendProcess()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CGlobalModule::OnSuspendProcess");
  OutputDebugStringA(
    " but did not override the method in its CGlobalModule implementation.  Please check the method signature to make sur"
    "e it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002fe0  sub     rsp, 28h
0x180002fe4  lea     rcx, OutputString; "This module subscribed to event "
0x180002feb  call    cs:__imp_OutputDebugStringA
0x180002ff1  lea     rcx, aCglobalmoduleO; "CGlobalModule::OnSuspendProcess"
0x180002ff8  call    cs:__imp_OutputDebugStringA
0x180002ffe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003005  call    cs:__imp_OutputDebugStringA
0x18000300b  call    cs:__imp_DebugBreak
0x180003011  xor     eax, eax
0x180003013  add     rsp, 28h
0x180003017  retn
```
