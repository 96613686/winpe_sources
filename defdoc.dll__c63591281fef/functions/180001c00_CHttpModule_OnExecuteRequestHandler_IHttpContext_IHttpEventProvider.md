# CHttpModule::OnExecuteRequestHandler(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001c00`
- end: `0x180001c38`
- name: `?OnExecuteRequestHandler@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c0b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c18`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c25`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c0b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c18`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c25`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001c2b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001c2b`

## pseudocode

```c
__int64 CHttpModule::OnExecuteRequestHandler()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnExecuteRequestHandler");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001c00  sub     rsp, 28h
0x180001c04  lea     rcx, OutputString; "This module subscribed to event "
0x180001c0b  call    cs:__imp_OutputDebugStringA
0x180001c11  lea     rcx, aChttpmoduleOne; "CHttpModule::OnExecuteRequestHandler"
0x180001c18  call    cs:__imp_OutputDebugStringA
0x180001c1e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001c25  call    cs:__imp_OutputDebugStringA
0x180001c2b  call    cs:__imp_DebugBreak
0x180001c31  xor     eax, eax
0x180001c33  add     rsp, 28h
0x180001c37  retn
```
