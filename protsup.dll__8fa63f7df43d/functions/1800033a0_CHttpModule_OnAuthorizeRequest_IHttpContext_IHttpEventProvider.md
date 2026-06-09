# CHttpModule::OnAuthorizeRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800033a0`
- end: `0x1800033d8`
- name: `?OnAuthorizeRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800033ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800033b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800033c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800033ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800033b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800033c5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800033cb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800033cb`

## pseudocode

```c
__int64 CHttpModule::OnAuthorizeRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnAuthorizeRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800033a0  sub     rsp, 28h
0x1800033a4  lea     rcx, OutputString; "This module subscribed to event "
0x1800033ab  call    cs:__imp_OutputDebugStringA
0x1800033b1  lea     rcx, aChttpmoduleOna; "CHttpModule::OnAuthorizeRequest"
0x1800033b8  call    cs:__imp_OutputDebugStringA
0x1800033be  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800033c5  call    cs:__imp_OutputDebugStringA
0x1800033cb  call    cs:__imp_DebugBreak
0x1800033d1  xor     eax, eax
0x1800033d3  add     rsp, 28h
0x1800033d7  retn
```
