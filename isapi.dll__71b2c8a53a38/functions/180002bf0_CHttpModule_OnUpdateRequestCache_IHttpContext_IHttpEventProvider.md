# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002bf0`
- end: `0x180002c28`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002bfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c15`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002bfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c15`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002c1b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002c1b`

## string_xrefs

- `0x180002c01`: `CHttpModule::OnUpdateRequestCache`

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
0x180002bf0  sub     rsp, 28h
0x180002bf4  lea     rcx, aThisModuleSubs; "This module subscribed to event "
0x180002bfb  call    cs:__imp_OutputDebugStringA
0x180002c01  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x180002c08  call    cs:__imp_OutputDebugStringA
0x180002c0e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180002c15  call    cs:__imp_OutputDebugStringA
0x180002c1b  call    cs:__imp_DebugBreak
0x180002c21  xor     eax, eax
0x180002c23  add     rsp, 28h
0x180002c27  retn
```
