# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003dc0`
- end: `0x180003df8`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003dcb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003dd8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003de5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003dcb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003dd8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003de5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003deb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003deb`

## string_xrefs

- `0x180003dd1`: `CHttpModule::OnResolveRequestCache`

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
0x180003dc0  sub     rsp, 28h
0x180003dc4  lea     rcx, OutputString; "This module subscribed to event "
0x180003dcb  call    cs:__imp_OutputDebugStringA
0x180003dd1  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x180003dd8  call    cs:__imp_OutputDebugStringA
0x180003dde  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180003de5  call    cs:__imp_OutputDebugStringA
0x180003deb  call    cs:__imp_DebugBreak
0x180003df1  xor     eax, eax
0x180003df3  add     rsp, 28h
0x180003df7  retn
```
