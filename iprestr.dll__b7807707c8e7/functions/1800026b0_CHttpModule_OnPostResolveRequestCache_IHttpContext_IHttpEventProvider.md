# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800026b0`
- end: `0x1800026e8`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800026bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800026c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800026d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800026bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800026c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800026d5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800026db`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800026db`

## string_xrefs

- `0x1800026c1`: `CHttpModule::OnPostResolveRequestCache`

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
0x1800026b0  sub     rsp, 28h
0x1800026b4  lea     rcx, OutputString; "This module subscribed to event "
0x1800026bb  call    cs:__imp_OutputDebugStringA
0x1800026c1  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x1800026c8  call    cs:__imp_OutputDebugStringA
0x1800026ce  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800026d5  call    cs:__imp_OutputDebugStringA
0x1800026db  call    cs:__imp_DebugBreak
0x1800026e1  xor     eax, eax
0x1800026e3  add     rsp, 28h
0x1800026e7  retn
```
