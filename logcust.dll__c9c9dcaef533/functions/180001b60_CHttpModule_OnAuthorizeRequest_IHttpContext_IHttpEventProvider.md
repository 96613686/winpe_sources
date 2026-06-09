# CHttpModule::OnAuthorizeRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001b60`
- end: `0x180001b98`
- name: `?OnAuthorizeRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b85`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b85`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001b8b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001b8b`

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
0x180001b60  sub     rsp, 28h
0x180001b64  lea     rcx, OutputString; "This module subscribed to event "
0x180001b6b  call    cs:__imp_OutputDebugStringA
0x180001b71  lea     rcx, aChttpmoduleOna; "CHttpModule::OnAuthorizeRequest"
0x180001b78  call    cs:__imp_OutputDebugStringA
0x180001b7e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001b85  call    cs:__imp_OutputDebugStringA
0x180001b8b  call    cs:__imp_DebugBreak
0x180001b91  xor     eax, eax
0x180001b93  add     rsp, 28h
0x180001b97  retn
```
