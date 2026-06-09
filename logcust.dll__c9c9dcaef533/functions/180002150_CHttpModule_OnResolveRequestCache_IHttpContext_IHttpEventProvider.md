# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002150`
- end: `0x180002188`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000215b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002168`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002175`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000215b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002168`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002175`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000217b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000217b`

## string_xrefs

- `0x180002161`: `CHttpModule::OnResolveRequestCache`

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
0x180002150  sub     rsp, 28h
0x180002154  lea     rcx, OutputString; "This module subscribed to event "
0x18000215b  call    cs:__imp_OutputDebugStringA
0x180002161  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x180002168  call    cs:__imp_OutputDebugStringA
0x18000216e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002175  call    cs:__imp_OutputDebugStringA
0x18000217b  call    cs:__imp_DebugBreak
0x180002181  xor     eax, eax
0x180002183  add     rsp, 28h
0x180002187  retn
```
