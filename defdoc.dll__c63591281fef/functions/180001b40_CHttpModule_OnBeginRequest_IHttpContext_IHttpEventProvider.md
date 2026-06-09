# CHttpModule::OnBeginRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001b40`
- end: `0x180001b78`
- name: `?OnBeginRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b58`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b65`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b58`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b65`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001b6b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001b6b`

## pseudocode

```c
__int64 CHttpModule::OnBeginRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnBeginRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001b40  sub     rsp, 28h
0x180001b44  lea     rcx, OutputString; "This module subscribed to event "
0x180001b4b  call    cs:__imp_OutputDebugStringA
0x180001b51  lea     rcx, aChttpmoduleOnb; "CHttpModule::OnBeginRequest"
0x180001b58  call    cs:__imp_OutputDebugStringA
0x180001b5e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001b65  call    cs:__imp_OutputDebugStringA
0x180001b6b  call    cs:__imp_DebugBreak
0x180001b71  xor     eax, eax
0x180001b73  add     rsp, 28h
0x180001b77  retn
```
