# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002930`
- end: `0x180002968`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000293b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002948`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002955`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000293b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002948`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002955`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000295b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000295b`

## string_xrefs

- `0x180002941`: `CHttpModule::OnPostResolveRequestCache`

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
0x180002930  sub     rsp, 28h
0x180002934  lea     rcx, aThisModuleSubs; "This module subscribed to event "
0x18000293b  call    cs:__imp_OutputDebugStringA
0x180002941  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x180002948  call    cs:__imp_OutputDebugStringA
0x18000294e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180002955  call    cs:__imp_OutputDebugStringA
0x18000295b  call    cs:__imp_DebugBreak
0x180002961  xor     eax, eax
0x180002963  add     rsp, 28h
0x180002967  retn
```
