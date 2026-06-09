# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180004320`
- end: `0x180004358`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000434b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000434b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000432b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004338`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004345`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000432b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004338`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004345`

## string_xrefs

- `0x180004331`: `CHttpModule::OnResolveRequestCache`

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
0x180004320  sub     rsp, 28h
0x180004324  lea     rcx, OutputString; "This module subscribed to event "
0x18000432b  call    cs:__imp_OutputDebugStringA
0x180004331  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x180004338  call    cs:__imp_OutputDebugStringA
0x18000433e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180004345  call    cs:__imp_OutputDebugStringA
0x18000434b  call    cs:__imp_DebugBreak
0x180004351  xor     eax, eax
0x180004353  add     rsp, 28h
0x180004357  retn
```
