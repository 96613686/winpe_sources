# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003840`
- end: `0x180003878`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000384b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003858`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003865`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000384b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003858`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003865`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000386b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000386b`

## string_xrefs

- `0x180003851`: `CHttpModule::OnPostResolveRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnPostResolveRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostResolveRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180003840  sub     rsp, 28h
0x180003844  lea     rcx, OutputString; "This module subscribed to event "
0x18000384b  call    cs:__imp_OutputDebugStringA
0x180003851  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x180003858  call    cs:__imp_OutputDebugStringA
0x18000385e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003865  call    cs:__imp_OutputDebugStringA
0x18000386b  call    cs:__imp_DebugBreak
0x180003871  xor     eax, eax
0x180003873  add     rsp, 28h
0x180003877  retn
```
