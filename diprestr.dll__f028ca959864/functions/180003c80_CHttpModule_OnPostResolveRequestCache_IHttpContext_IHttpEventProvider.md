# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003c80`
- end: `0x180003cb8`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003c8b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003c98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003ca5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003c8b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003c98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003ca5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003cab`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003cab`

## string_xrefs

- `0x180003c91`: `CHttpModule::OnPostResolveRequestCache`

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
0x180003c80  sub     rsp, 28h
0x180003c84  lea     rcx, OutputString; "This module subscribed to event "
0x180003c8b  call    cs:__imp_OutputDebugStringA
0x180003c91  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x180003c98  call    cs:__imp_OutputDebugStringA
0x180003c9e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180003ca5  call    cs:__imp_OutputDebugStringA
0x180003cab  call    cs:__imp_DebugBreak
0x180003cb1  xor     eax, eax
0x180003cb3  add     rsp, 28h
0x180003cb7  retn
```
