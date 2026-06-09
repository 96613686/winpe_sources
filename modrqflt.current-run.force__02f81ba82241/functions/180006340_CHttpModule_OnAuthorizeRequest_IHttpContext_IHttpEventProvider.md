# CHttpModule::OnAuthorizeRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180006340`
- end: `0x180006378`
- name: `?OnAuthorizeRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000636b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000636b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000634b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006358`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006365`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000634b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006358`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006365`

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
0x180006340  sub     rsp, 28h
0x180006344  lea     rcx, OutputString; "This module subscribed to event "
0x18000634b  call    cs:__imp_OutputDebugStringA
0x180006351  lea     rcx, aChttpmoduleOna; "CHttpModule::OnAuthorizeRequest"
0x180006358  call    cs:__imp_OutputDebugStringA
0x18000635e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180006365  call    cs:__imp_OutputDebugStringA
0x18000636b  call    cs:__imp_DebugBreak
0x180006371  xor     eax, eax
0x180006373  add     rsp, 28h
0x180006377  retn
```
