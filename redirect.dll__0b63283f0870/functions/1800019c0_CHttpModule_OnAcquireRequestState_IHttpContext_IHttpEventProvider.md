# CHttpModule::OnAcquireRequestState(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800019c0`
- end: `0x1800019f8`
- name: `?OnAcquireRequestState@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800019cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800019d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800019e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800019cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800019d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800019e5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800019eb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800019eb`

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
0x1800019c0  sub     rsp, 28h
0x1800019c4  lea     rcx, OutputString; "This module subscribed to event "
0x1800019cb  call    cs:__imp_OutputDebugStringA
0x1800019d1  lea     rcx, aChttpmoduleOna_0; "CHttpModule::OnAcquireRequestState"
0x1800019d8  call    cs:__imp_OutputDebugStringA
0x1800019de  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800019e5  call    cs:__imp_OutputDebugStringA
0x1800019eb  call    cs:__imp_DebugBreak
0x1800019f1  xor     eax, eax
0x1800019f3  add     rsp, 28h
0x1800019f7  retn
```
