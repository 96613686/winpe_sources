# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180007e10`
- end: `0x180007e48`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007e1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007e28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007e35`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007e1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007e28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007e35`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180007e3b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180007e3b`

## string_xrefs

- `0x180007e21`: `CHttpModule::OnResolveRequestCache`

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
0x180007e10  sub     rsp, 28h
0x180007e14  lea     rcx, OutputString; "This module subscribed to event "
0x180007e1b  call    cs:__imp_OutputDebugStringA
0x180007e21  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x180007e28  call    cs:__imp_OutputDebugStringA
0x180007e2e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180007e35  call    cs:__imp_OutputDebugStringA
0x180007e3b  call    cs:__imp_DebugBreak
0x180007e41  xor     eax, eax
0x180007e43  add     rsp, 28h
0x180007e47  retn
```
