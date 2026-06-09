# CHttpModule::OnLogRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001bf0`
- end: `0x180001c28`
- name: `?OnLogRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c15`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c15`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001c1b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001c1b`

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
0x180001bf0  sub     rsp, 28h
0x180001bf4  lea     rcx, OutputString; "This module subscribed to event "
0x180001bfb  call    cs:__imp_OutputDebugStringA
0x180001c01  lea     rcx, aChttpmoduleOnl; "CHttpModule::OnLogRequest"
0x180001c08  call    cs:__imp_OutputDebugStringA
0x180001c0e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001c15  call    cs:__imp_OutputDebugStringA
0x180001c1b  call    cs:__imp_DebugBreak
0x180001c21  xor     eax, eax
0x180001c23  add     rsp, 28h
0x180001c27  retn
```
