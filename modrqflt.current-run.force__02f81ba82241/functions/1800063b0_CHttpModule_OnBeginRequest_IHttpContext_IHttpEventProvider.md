# CHttpModule::OnBeginRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800063b0`
- end: `0x1800063e8`
- name: `?OnBeginRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800063db`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800063db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800063bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800063c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800063d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800063bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800063c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800063d5`

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
0x1800063b0  sub     rsp, 28h
0x1800063b4  lea     rcx, OutputString; "This module subscribed to event "
0x1800063bb  call    cs:__imp_OutputDebugStringA
0x1800063c1  lea     rcx, aChttpmoduleOnb; "CHttpModule::OnBeginRequest"
0x1800063c8  call    cs:__imp_OutputDebugStringA
0x1800063ce  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800063d5  call    cs:__imp_OutputDebugStringA
0x1800063db  call    cs:__imp_DebugBreak
0x1800063e1  xor     eax, eax
0x1800063e3  add     rsp, 28h
0x1800063e7  retn
```
