# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180004490`
- end: `0x1800044c8`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000449b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800044a8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800044b5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000449b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800044a8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800044b5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800044bb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800044bb`

## string_xrefs

- `0x1800044a1`: `CHttpModule::OnResolveRequestCache`

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
0x180004490  sub     rsp, 28h
0x180004494  lea     rcx, OutputString; "This module subscribed to event "
0x18000449b  call    cs:__imp_OutputDebugStringA
0x1800044a1  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x1800044a8  call    cs:__imp_OutputDebugStringA
0x1800044ae  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800044b5  call    cs:__imp_OutputDebugStringA
0x1800044bb  call    cs:__imp_DebugBreak
0x1800044c1  xor     eax, eax
0x1800044c3  add     rsp, 28h
0x1800044c7  retn
```
