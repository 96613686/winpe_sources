# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800020c0`
- end: `0x1800020f8`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800020eb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800020eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020e5`

## string_xrefs

- `0x1800020d1`: `CHttpModule::OnResolveRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnResolveRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnResolveRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800020c0  sub     rsp, 28h
0x1800020c4  lea     rcx, OutputString; "This module subscribed to event "
0x1800020cb  call    cs:__imp_OutputDebugStringA
0x1800020d1  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x1800020d8  call    cs:__imp_OutputDebugStringA
0x1800020de  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800020e5  call    cs:__imp_OutputDebugStringA
0x1800020eb  call    cs:__imp_DebugBreak
0x1800020f1  xor     eax, eax
0x1800020f3  add     rsp, 28h
0x1800020f7  retn
```
