# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003030`
- end: `0x180003068`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000305b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000305b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000303b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003048`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003055`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000303b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003048`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003055`

## string_xrefs

- `0x180003041`: `CHttpModule::OnResolveRequestCache`

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
0x180003030  sub     rsp, 28h
0x180003034  lea     rcx, OutputString; "This module subscribed to event "
0x18000303b  call    cs:__imp_OutputDebugStringA
0x180003041  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x180003048  call    cs:__imp_OutputDebugStringA
0x18000304e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180003055  call    cs:__imp_OutputDebugStringA
0x18000305b  call    cs:__imp_DebugBreak
0x180003061  xor     eax, eax
0x180003063  add     rsp, 28h
0x180003067  retn
```
