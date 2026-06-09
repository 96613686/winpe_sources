# CHttpModule::OnPostUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003880`
- end: `0x1800038b8`
- name: `?OnPostUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000388b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003898`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800038a5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000388b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003898`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800038a5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800038ab`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800038ab`

## string_xrefs

- `0x180003891`: `CHttpModule::OnPostUpdateRequestCache`

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
0x180003880  sub     rsp, 28h
0x180003884  lea     rcx, OutputString; "This module subscribed to event "
0x18000388b  call    cs:__imp_OutputDebugStringA
0x180003891  lea     rcx, aChttpmoduleOnp; "CHttpModule::OnPostUpdateRequestCache"
0x180003898  call    cs:__imp_OutputDebugStringA
0x18000389e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800038a5  call    cs:__imp_OutputDebugStringA
0x1800038ab  call    cs:__imp_DebugBreak
0x1800038b1  xor     eax, eax
0x1800038b3  add     rsp, 28h
0x1800038b7  retn
```
