# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180006c80`
- end: `0x180006cb8`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180006cab`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180006cab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006c8b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006c98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006ca5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006c8b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006c98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006ca5`

## string_xrefs

- `0x180006c91`: `CHttpModule::OnResolveRequestCache`

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
0x180006c80  sub     rsp, 28h
0x180006c84  lea     rcx, OutputString; "This module subscribed to event "
0x180006c8b  call    cs:__imp_OutputDebugStringA
0x180006c91  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x180006c98  call    cs:__imp_OutputDebugStringA
0x180006c9e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180006ca5  call    cs:__imp_OutputDebugStringA
0x180006cab  call    cs:__imp_DebugBreak
0x180006cb1  xor     eax, eax
0x180006cb3  add     rsp, 28h
0x180006cb7  retn
```
