# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800020b0`
- end: `0x1800020e8`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800020db`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800020db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020d5`

## string_xrefs

- `0x1800020c1`: `CHttpModule::OnResolveRequestCache`

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
0x1800020b0  sub     rsp, 28h
0x1800020b4  lea     rcx, OutputString; "This module subscribed to event "
0x1800020bb  call    cs:__imp_OutputDebugStringA
0x1800020c1  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x1800020c8  call    cs:__imp_OutputDebugStringA
0x1800020ce  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800020d5  call    cs:__imp_OutputDebugStringA
0x1800020db  call    cs:__imp_DebugBreak
0x1800020e1  xor     eax, eax
0x1800020e3  add     rsp, 28h
0x1800020e7  retn
```
