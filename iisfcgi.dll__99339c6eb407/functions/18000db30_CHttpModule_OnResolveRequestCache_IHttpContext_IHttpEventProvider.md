# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x18000db30`
- end: `0x18000db68`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000db5b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000db5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000db3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000db48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000db55`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000db3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000db48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000db55`

## string_xrefs

- `0x18000db41`: `CHttpModule::OnResolveRequestCache`

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
0x18000db30  sub     rsp, 28h
0x18000db34  lea     rcx, OutputString; "This module subscribed to event "
0x18000db3b  call    cs:__imp_OutputDebugStringA
0x18000db41  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x18000db48  call    cs:__imp_OutputDebugStringA
0x18000db4e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x18000db55  call    cs:__imp_OutputDebugStringA
0x18000db5b  call    cs:__imp_DebugBreak
0x18000db61  xor     eax, eax
0x18000db63  add     rsp, 28h
0x18000db67  retn
```
