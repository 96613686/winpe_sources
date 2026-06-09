# CHttpModule::OnAuthenticateRequest(IHttpContext *,IAuthenticationProvider *)

- ea: `0x180003360`
- end: `0x180003398`
- name: `?OnAuthenticateRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIAuthenticationProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000336b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003378`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003385`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000336b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003378`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003385`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000338b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000338b`

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
0x180003360  sub     rsp, 28h
0x180003364  lea     rcx, OutputString; "This module subscribed to event "
0x18000336b  call    cs:__imp_OutputDebugStringA
0x180003371  lea     rcx, aChttpmoduleOna_2; "CHttpModule::OnAuthenticateRequest"
0x180003378  call    cs:__imp_OutputDebugStringA
0x18000337e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003385  call    cs:__imp_OutputDebugStringA
0x18000338b  call    cs:__imp_DebugBreak
0x180003391  xor     eax, eax
0x180003393  add     rsp, 28h
0x180003397  retn
```
