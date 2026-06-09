# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180009e40`
- end: `0x180009e78`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180009e6b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180009e6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009e4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009e58`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009e65`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009e4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009e58`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009e65`

## string_xrefs

- `0x180009e51`: `CHttpModule::OnResolveRequestCache`

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
0x180009e40  sub     rsp, 28h
0x180009e44  lea     rcx, OutputString; "This module subscribed to event "
0x180009e4b  call    cs:__imp_OutputDebugStringA
0x180009e51  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x180009e58  call    cs:__imp_OutputDebugStringA
0x180009e5e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180009e65  call    cs:__imp_OutputDebugStringA
0x180009e6b  call    cs:__imp_DebugBreak
0x180009e71  xor     eax, eax
0x180009e73  add     rsp, 28h
0x180009e77  retn
```
