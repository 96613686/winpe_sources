# CHttpModule::OnPostBeginRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001da0`
- end: `0x180001dd8`
- name: `?OnPostBeginRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001dab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001db8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001dc5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001dab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001db8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001dc5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001dcb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001dcb`

## pseudocode

```c
__int64 CHttpModule::OnPostBeginRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostBeginRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001da0  sub     rsp, 28h
0x180001da4  lea     rcx, OutputString; "This module subscribed to event "
0x180001dab  call    cs:__imp_OutputDebugStringA
0x180001db1  lea     rcx, aChttpmoduleOnp_10; "CHttpModule::OnPostBeginRequest"
0x180001db8  call    cs:__imp_OutputDebugStringA
0x180001dbe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001dc5  call    cs:__imp_OutputDebugStringA
0x180001dcb  call    cs:__imp_DebugBreak
0x180001dd1  xor     eax, eax
0x180001dd3  add     rsp, 28h
0x180001dd7  retn
```
