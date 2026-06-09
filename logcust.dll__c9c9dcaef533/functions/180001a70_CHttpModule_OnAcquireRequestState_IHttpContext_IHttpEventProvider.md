# CHttpModule::OnAcquireRequestState(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001a70`
- end: `0x180001aa8`
- name: `?OnAcquireRequestState@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a95`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001a9b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001a9b`

## pseudocode

```c
__int64 CHttpModule::OnAcquireRequestState()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnAcquireRequestState");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001a70  sub     rsp, 28h
0x180001a74  lea     rcx, OutputString; "This module subscribed to event "
0x180001a7b  call    cs:__imp_OutputDebugStringA
0x180001a81  lea     rcx, aChttpmoduleOna_0; "CHttpModule::OnAcquireRequestState"
0x180001a88  call    cs:__imp_OutputDebugStringA
0x180001a8e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001a95  call    cs:__imp_OutputDebugStringA
0x180001a9b  call    cs:__imp_DebugBreak
0x180001aa1  xor     eax, eax
0x180001aa3  add     rsp, 28h
0x180001aa7  retn
```
