# CHttpModule::OnPostLogRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001eb0`
- end: `0x180001ee8`
- name: `?OnPostLogRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ebb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ec8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ed5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ebb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ec8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ed5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001edb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001edb`

## pseudocode

```c
__int64 CHttpModule::OnPostLogRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostLogRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001eb0  sub     rsp, 28h
0x180001eb4  lea     rcx, OutputString; "This module subscribed to event "
0x180001ebb  call    cs:__imp_OutputDebugStringA
0x180001ec1  lea     rcx, aChttpmoduleOnp_11; "CHttpModule::OnPostLogRequest"
0x180001ec8  call    cs:__imp_OutputDebugStringA
0x180001ece  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001ed5  call    cs:__imp_OutputDebugStringA
0x180001edb  call    cs:__imp_DebugBreak
0x180001ee1  xor     eax, eax
0x180001ee3  add     rsp, 28h
0x180001ee7  retn
```
