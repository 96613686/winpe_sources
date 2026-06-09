# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180009c90`
- end: `0x180009cc8`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180009cbb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180009cbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009c9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009ca8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009cb5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009c9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009ca8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009cb5`

## string_xrefs

- `0x180009ca1`: `CHttpModule::OnPostResolveRequestCache`

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
0x180009c90  sub     rsp, 28h
0x180009c94  lea     rcx, OutputString; "This module subscribed to event "
0x180009c9b  call    cs:__imp_OutputDebugStringA
0x180009ca1  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x180009ca8  call    cs:__imp_OutputDebugStringA
0x180009cae  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180009cb5  call    cs:__imp_OutputDebugStringA
0x180009cbb  call    cs:__imp_DebugBreak
0x180009cc1  xor     eax, eax
0x180009cc3  add     rsp, 28h
0x180009cc7  retn
```
