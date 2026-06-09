# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180007c70`
- end: `0x180007ca8`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007c7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007c88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007c95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007c7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007c88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007c95`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180007c9b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180007c9b`

## string_xrefs

- `0x180007c81`: `CHttpModule::OnPostResolveRequestCache`

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
0x180007c70  sub     rsp, 28h
0x180007c74  lea     rcx, OutputString; "This module subscribed to event "
0x180007c7b  call    cs:__imp_OutputDebugStringA
0x180007c81  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x180007c88  call    cs:__imp_OutputDebugStringA
0x180007c8e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180007c95  call    cs:__imp_OutputDebugStringA
0x180007c9b  call    cs:__imp_DebugBreak
0x180007ca1  xor     eax, eax
0x180007ca3  add     rsp, 28h
0x180007ca7  retn
```
