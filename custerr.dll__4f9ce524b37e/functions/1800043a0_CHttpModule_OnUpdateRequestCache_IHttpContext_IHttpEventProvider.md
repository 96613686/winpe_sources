# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800043a0`
- end: `0x1800043d8`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800043cb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800043cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800043ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800043b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800043c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800043ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800043b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800043c5`

## string_xrefs

- `0x1800043b1`: `CHttpModule::OnUpdateRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnUpdateRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnUpdateRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800043a0  sub     rsp, 28h
0x1800043a4  lea     rcx, OutputString; "This module subscribed to event "
0x1800043ab  call    cs:__imp_OutputDebugStringA
0x1800043b1  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x1800043b8  call    cs:__imp_OutputDebugStringA
0x1800043be  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800043c5  call    cs:__imp_OutputDebugStringA
0x1800043cb  call    cs:__imp_DebugBreak
0x1800043d1  xor     eax, eax
0x1800043d3  add     rsp, 28h
0x1800043d7  retn
```
