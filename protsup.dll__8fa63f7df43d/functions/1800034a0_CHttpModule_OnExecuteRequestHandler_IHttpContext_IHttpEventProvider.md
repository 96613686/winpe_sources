# CHttpModule::OnExecuteRequestHandler(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800034a0`
- end: `0x1800034d8`
- name: `?OnExecuteRequestHandler@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800034ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800034b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800034c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800034ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800034b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800034c5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800034cb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800034cb`

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
0x1800034a0  sub     rsp, 28h
0x1800034a4  lea     rcx, OutputString; "This module subscribed to event "
0x1800034ab  call    cs:__imp_OutputDebugStringA
0x1800034b1  lea     rcx, aChttpmoduleOne; "CHttpModule::OnExecuteRequestHandler"
0x1800034b8  call    cs:__imp_OutputDebugStringA
0x1800034be  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800034c5  call    cs:__imp_OutputDebugStringA
0x1800034cb  call    cs:__imp_DebugBreak
0x1800034d1  xor     eax, eax
0x1800034d3  add     rsp, 28h
0x1800034d7  retn
```
