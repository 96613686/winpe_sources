# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002350`
- end: `0x180002388`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000235b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002368`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002375`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000235b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002368`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002375`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000237b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000237b`

## string_xrefs

- `0x180002361`: `CHttpModule::OnResolveRequestCache`

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
0x180002350  sub     rsp, 28h
0x180002354  lea     rcx, OutputString; "This module subscribed to event "
0x18000235b  call    cs:__imp_OutputDebugStringA
0x180002361  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x180002368  call    cs:__imp_OutputDebugStringA
0x18000236e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180002375  call    cs:__imp_OutputDebugStringA
0x18000237b  call    cs:__imp_DebugBreak
0x180002381  xor     eax, eax
0x180002383  add     rsp, 28h
0x180002387  retn
```
