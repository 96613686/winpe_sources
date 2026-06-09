# CHttpModule::OnMapRequestHandler(IHttpContext *,IMapHandlerProvider *)

- ea: `0x180001cf0`
- end: `0x180001d28`
- name: `?OnMapRequestHandler@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapHandlerProvider@@@Z`
- size: `56`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d15`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d15`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d1b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d1b`

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
0x180001cf0  sub     rsp, 28h
0x180001cf4  lea     rcx, OutputString; "This module subscribed to event "
0x180001cfb  call    cs:__imp_OutputDebugStringA
0x180001d01  lea     rcx, aChttpmoduleOnm; "CHttpModule::OnMapRequestHandler"
0x180001d08  call    cs:__imp_OutputDebugStringA
0x180001d0e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001d15  call    cs:__imp_OutputDebugStringA
0x180001d1b  call    cs:__imp_DebugBreak
0x180001d21  xor     eax, eax
0x180001d23  add     rsp, 28h
0x180001d27  retn
```
