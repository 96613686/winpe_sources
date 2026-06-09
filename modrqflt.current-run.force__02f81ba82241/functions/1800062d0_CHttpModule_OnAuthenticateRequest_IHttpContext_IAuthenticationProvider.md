# CHttpModule::OnAuthenticateRequest(IHttpContext *,IAuthenticationProvider *)

- ea: `0x1800062d0`
- end: `0x180006308`
- name: `?OnAuthenticateRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIAuthenticationProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800062fb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800062fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800062db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800062e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800062f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800062db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800062e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800062f5`

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
0x1800062d0  sub     rsp, 28h
0x1800062d4  lea     rcx, OutputString; "This module subscribed to event "
0x1800062db  call    cs:__imp_OutputDebugStringA
0x1800062e1  lea     rcx, aChttpmoduleOna_2; "CHttpModule::OnAuthenticateRequest"
0x1800062e8  call    cs:__imp_OutputDebugStringA
0x1800062ee  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800062f5  call    cs:__imp_OutputDebugStringA
0x1800062fb  call    cs:__imp_DebugBreak
0x180006301  xor     eax, eax
0x180006303  add     rsp, 28h
0x180006307  retn
```
