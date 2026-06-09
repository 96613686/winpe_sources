# CHttpModule::OnPostAuthorizeRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001d80`
- end: `0x180001db8`
- name: `?OnPostAuthorizeRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001dab`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001dab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d8b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001da5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d8b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001da5`

## pseudocode

```c
__int64 CHttpModule::OnPostAuthorizeRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostAuthorizeRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001d80  sub     rsp, 28h
0x180001d84  lea     rcx, OutputString; "This module subscribed to event "
0x180001d8b  call    cs:__imp_OutputDebugStringA
0x180001d91  lea     rcx, aChttpmoduleOnp_3; "CHttpModule::OnPostAuthorizeRequest"
0x180001d98  call    cs:__imp_OutputDebugStringA
0x180001d9e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001da5  call    cs:__imp_OutputDebugStringA
0x180001dab  call    cs:__imp_DebugBreak
0x180001db1  xor     eax, eax
0x180001db3  add     rsp, 28h
0x180001db7  retn
```
