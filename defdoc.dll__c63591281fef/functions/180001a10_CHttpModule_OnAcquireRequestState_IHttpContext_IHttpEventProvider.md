# CHttpModule::OnAcquireRequestState(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001a10`
- end: `0x180001a48`
- name: `?OnAcquireRequestState@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a35`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a35`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001a3b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001a3b`

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
0x180001a10  sub     rsp, 28h
0x180001a14  lea     rcx, OutputString; "This module subscribed to event "
0x180001a1b  call    cs:__imp_OutputDebugStringA
0x180001a21  lea     rcx, aChttpmoduleOna_0; "CHttpModule::OnAcquireRequestState"
0x180001a28  call    cs:__imp_OutputDebugStringA
0x180001a2e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001a35  call    cs:__imp_OutputDebugStringA
0x180001a3b  call    cs:__imp_DebugBreak
0x180001a41  xor     eax, eax
0x180001a43  add     rsp, 28h
0x180001a47  retn
```
