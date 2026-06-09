# CHttpModule::OnAuthorizeRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001ae0`
- end: `0x180001b18`
- name: `?OnAuthorizeRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001b0b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001b0b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001aeb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001af8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b05`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001aeb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001af8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b05`

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
0x180001ae0  sub     rsp, 28h
0x180001ae4  lea     rcx, OutputString; "This module subscribed to event "
0x180001aeb  call    cs:__imp_OutputDebugStringA
0x180001af1  lea     rcx, aChttpmoduleOna; "CHttpModule::OnAuthorizeRequest"
0x180001af8  call    cs:__imp_OutputDebugStringA
0x180001afe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001b05  call    cs:__imp_OutputDebugStringA
0x180001b0b  call    cs:__imp_DebugBreak
0x180001b11  xor     eax, eax
0x180001b13  add     rsp, 28h
0x180001b17  retn
```
