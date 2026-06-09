# CHttpModule::OnPostUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180004220`
- end: `0x180004258`
- name: `?OnPostUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000424b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000424b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000422b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004238`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004245`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000422b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004238`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004245`

## string_xrefs

- `0x180004231`: `CHttpModule::OnPostUpdateRequestCache`

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
0x180004220  sub     rsp, 28h
0x180004224  lea     rcx, OutputString; "This module subscribed to event "
0x18000422b  call    cs:__imp_OutputDebugStringA
0x180004231  lea     rcx, aChttpmoduleOnp; "CHttpModule::OnPostUpdateRequestCache"
0x180004238  call    cs:__imp_OutputDebugStringA
0x18000423e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180004245  call    cs:__imp_OutputDebugStringA
0x18000424b  call    cs:__imp_DebugBreak
0x180004251  xor     eax, eax
0x180004253  add     rsp, 28h
0x180004257  retn
```
