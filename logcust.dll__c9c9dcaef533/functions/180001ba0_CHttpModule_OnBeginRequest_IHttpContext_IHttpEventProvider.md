# CHttpModule::OnBeginRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001ba0`
- end: `0x180001bd8`
- name: `?OnBeginRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bc5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bc5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001bcb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001bcb`

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
0x180001ba0  sub     rsp, 28h
0x180001ba4  lea     rcx, OutputString; "This module subscribed to event "
0x180001bab  call    cs:__imp_OutputDebugStringA
0x180001bb1  lea     rcx, aChttpmoduleOnb; "CHttpModule::OnBeginRequest"
0x180001bb8  call    cs:__imp_OutputDebugStringA
0x180001bbe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001bc5  call    cs:__imp_OutputDebugStringA
0x180001bcb  call    cs:__imp_DebugBreak
0x180001bd1  xor     eax, eax
0x180001bd3  add     rsp, 28h
0x180001bd7  retn
```
