# CHttpModule::OnPostAcquireRequestState(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001ce0`
- end: `0x180001d18`
- name: `?OnPostAcquireRequestState@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ceb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cf8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d05`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ceb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cf8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d05`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d0b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d0b`

## pseudocode

```c
__int64 CHttpModule::OnPostAcquireRequestState()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostAcquireRequestState");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001ce0  sub     rsp, 28h
0x180001ce4  lea     rcx, OutputString; "This module subscribed to event "
0x180001ceb  call    cs:__imp_OutputDebugStringA
0x180001cf1  lea     rcx, aChttpmoduleOnp_7; "CHttpModule::OnPostAcquireRequestState"
0x180001cf8  call    cs:__imp_OutputDebugStringA
0x180001cfe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001d05  call    cs:__imp_OutputDebugStringA
0x180001d0b  call    cs:__imp_DebugBreak
0x180001d11  xor     eax, eax
0x180001d13  add     rsp, 28h
0x180001d17  retn
```
