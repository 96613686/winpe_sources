# CHttpModule::OnLogRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001ca0`
- end: `0x180001cd8`
- name: `?OnLogRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cc5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cc5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001ccb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001ccb`

## pseudocode

```c
__int64 CHttpModule::OnLogRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnLogRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001ca0  sub     rsp, 28h
0x180001ca4  lea     rcx, OutputString; "This module subscribed to event "
0x180001cab  call    cs:__imp_OutputDebugStringA
0x180001cb1  lea     rcx, aChttpmoduleOnl; "CHttpModule::OnLogRequest"
0x180001cb8  call    cs:__imp_OutputDebugStringA
0x180001cbe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001cc5  call    cs:__imp_OutputDebugStringA
0x180001ccb  call    cs:__imp_DebugBreak
0x180001cd1  xor     eax, eax
0x180001cd3  add     rsp, 28h
0x180001cd7  retn
```
