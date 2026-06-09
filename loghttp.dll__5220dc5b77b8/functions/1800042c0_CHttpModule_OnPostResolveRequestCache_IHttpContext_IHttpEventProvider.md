# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800042c0`
- end: `0x1800042f8`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800042cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800042d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800042e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800042cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800042d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800042e5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800042eb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800042eb`

## string_xrefs

- `0x1800042d1`: `CHttpModule::OnPostResolveRequestCache`

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
0x1800042c0  sub     rsp, 28h
0x1800042c4  lea     rcx, OutputString; "This module subscribed to event "
0x1800042cb  call    cs:__imp_OutputDebugStringA
0x1800042d1  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x1800042d8  call    cs:__imp_OutputDebugStringA
0x1800042de  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800042e5  call    cs:__imp_OutputDebugStringA
0x1800042eb  call    cs:__imp_DebugBreak
0x1800042f1  xor     eax, eax
0x1800042f3  add     rsp, 28h
0x1800042f7  retn
```
