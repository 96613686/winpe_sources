# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002870`
- end: `0x1800028a8`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000287b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002888`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002895`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000287b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002888`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002895`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000289b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000289b`

## string_xrefs

- `0x180002881`: `CHttpModule::OnUpdateRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnUpdateRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnUpdateRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002870  sub     rsp, 28h
0x180002874  lea     rcx, OutputString; "This module subscribed to event "
0x18000287b  call    cs:__imp_OutputDebugStringA
0x180002881  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x180002888  call    cs:__imp_OutputDebugStringA
0x18000288e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002895  call    cs:__imp_OutputDebugStringA
0x18000289b  call    cs:__imp_DebugBreak
0x1800028a1  xor     eax, eax
0x1800028a3  add     rsp, 28h
0x1800028a7  retn
```
