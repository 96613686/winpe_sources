# CHttpModule::OnAuthenticateRequest(IHttpContext *,IAuthenticationProvider *)

- ea: `0x180001aa0`
- end: `0x180001ad8`
- name: `?OnAuthenticateRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIAuthenticationProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001acb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001acb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001aab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ab8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ac5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001aab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ab8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ac5`

## pseudocode

```c
__int64 CHttpModule::OnAuthenticateRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnAuthenticateRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001aa0  sub     rsp, 28h
0x180001aa4  lea     rcx, OutputString; "This module subscribed to event "
0x180001aab  call    cs:__imp_OutputDebugStringA
0x180001ab1  lea     rcx, aChttpmoduleOna_2; "CHttpModule::OnAuthenticateRequest"
0x180001ab8  call    cs:__imp_OutputDebugStringA
0x180001abe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001ac5  call    cs:__imp_OutputDebugStringA
0x180001acb  call    cs:__imp_DebugBreak
0x180001ad1  xor     eax, eax
0x180001ad3  add     rsp, 28h
0x180001ad7  retn
```
