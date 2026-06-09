# CHttpModule::OnAuthorizeRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001ab0`
- end: `0x180001ae8`
- name: `?OnAuthorizeRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001abb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ac8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ad5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001abb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ac8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ad5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001adb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001adb`

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
0x180001ab0  sub     rsp, 28h
0x180001ab4  lea     rcx, OutputString; "This module subscribed to event "
0x180001abb  call    cs:__imp_OutputDebugStringA
0x180001ac1  lea     rcx, aChttpmoduleOna; "CHttpModule::OnAuthorizeRequest"
0x180001ac8  call    cs:__imp_OutputDebugStringA
0x180001ace  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001ad5  call    cs:__imp_OutputDebugStringA
0x180001adb  call    cs:__imp_DebugBreak
0x180001ae1  xor     eax, eax
0x180001ae3  add     rsp, 28h
0x180001ae7  retn
```
