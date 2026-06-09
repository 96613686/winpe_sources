# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800041e0`
- end: `0x180004218`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000420b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000420b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800041eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800041f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004205`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800041eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800041f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004205`

## string_xrefs

- `0x1800041f1`: `CHttpModule::OnPostResolveRequestCache`

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
0x1800041e0  sub     rsp, 28h
0x1800041e4  lea     rcx, OutputString; "This module subscribed to event "
0x1800041eb  call    cs:__imp_OutputDebugStringA
0x1800041f1  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x1800041f8  call    cs:__imp_OutputDebugStringA
0x1800041fe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180004205  call    cs:__imp_OutputDebugStringA
0x18000420b  call    cs:__imp_DebugBreak
0x180004211  xor     eax, eax
0x180004213  add     rsp, 28h
0x180004217  retn
```
