# CHttpModule::OnPostAuthenticateRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001d40`
- end: `0x180001d78`
- name: `?OnPostAuthenticateRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d6b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d58`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d65`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d58`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d65`

## pseudocode

```c
__int64 CHttpModule::OnPostAuthenticateRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostAuthenticateRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001d40  sub     rsp, 28h
0x180001d44  lea     rcx, OutputString; "This module subscribed to event "
0x180001d4b  call    cs:__imp_OutputDebugStringA
0x180001d51  lea     rcx, aChttpmoduleOnp_1; "CHttpModule::OnPostAuthenticateRequest"
0x180001d58  call    cs:__imp_OutputDebugStringA
0x180001d5e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001d65  call    cs:__imp_OutputDebugStringA
0x180001d6b  call    cs:__imp_DebugBreak
0x180001d71  xor     eax, eax
0x180001d73  add     rsp, 28h
0x180001d77  retn
```
