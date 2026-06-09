# CHttpModule::OnAuthenticateRequest(IHttpContext *,IAuthenticationProvider *)

- ea: `0x180001b20`
- end: `0x180001b58`
- name: `?OnAuthenticateRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIAuthenticationProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b2b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b38`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b45`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b2b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b38`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b45`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001b4b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001b4b`

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
0x180001b20  sub     rsp, 28h
0x180001b24  lea     rcx, OutputString; "This module subscribed to event "
0x180001b2b  call    cs:__imp_OutputDebugStringA
0x180001b31  lea     rcx, aChttpmoduleOna_2; "CHttpModule::OnAuthenticateRequest"
0x180001b38  call    cs:__imp_OutputDebugStringA
0x180001b3e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001b45  call    cs:__imp_OutputDebugStringA
0x180001b4b  call    cs:__imp_DebugBreak
0x180001b51  xor     eax, eax
0x180001b53  add     rsp, 28h
0x180001b57  retn
```
