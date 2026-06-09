# CHttpModule::OnMapRequestHandler(IHttpContext *,IMapHandlerProvider *)

- ea: `0x180001cc0`
- end: `0x180001cf8`
- name: `?OnMapRequestHandler@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapHandlerProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001ceb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001ceb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ccb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cd8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ce5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ccb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cd8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ce5`

## pseudocode

```c
__int64 CHttpModule::OnMapRequestHandler()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnMapRequestHandler");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001cc0  sub     rsp, 28h
0x180001cc4  lea     rcx, OutputString; "This module subscribed to event "
0x180001ccb  call    cs:__imp_OutputDebugStringA
0x180001cd1  lea     rcx, aChttpmoduleOnm; "CHttpModule::OnMapRequestHandler"
0x180001cd8  call    cs:__imp_OutputDebugStringA
0x180001cde  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001ce5  call    cs:__imp_OutputDebugStringA
0x180001ceb  call    cs:__imp_DebugBreak
0x180001cf1  xor     eax, eax
0x180001cf3  add     rsp, 28h
0x180001cf7  retn
```
