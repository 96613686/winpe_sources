# CHttpModule::OnPostUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800029a0`
- end: `0x1800029d8`
- name: `?OnPostUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029c5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800029cb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800029cb`

## string_xrefs

- `0x1800029b1`: `CHttpModule::OnPostUpdateRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnPostUpdateRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostUpdateRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800029a0  sub     rsp, 28h
0x1800029a4  lea     rcx, aThisModuleSubs; "This module subscribed to event "
0x1800029ab  call    cs:__imp_OutputDebugStringA
0x1800029b1  lea     rcx, aChttpmoduleOnp; "CHttpModule::OnPostUpdateRequestCache"
0x1800029b8  call    cs:__imp_OutputDebugStringA
0x1800029be  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x1800029c5  call    cs:__imp_OutputDebugStringA
0x1800029cb  call    cs:__imp_DebugBreak
0x1800029d1  xor     eax, eax
0x1800029d3  add     rsp, 28h
0x1800029d7  retn
```
