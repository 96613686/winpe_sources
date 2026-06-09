# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003e80`
- end: `0x180003eb8`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003e8b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003e98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003ea5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003e8b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003e98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003ea5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003eab`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003eab`

## string_xrefs

- `0x180003e91`: `CHttpModule::OnUpdateRequestCache`

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
0x180003e80  sub     rsp, 28h
0x180003e84  lea     rcx, OutputString; "This module subscribed to event "
0x180003e8b  call    cs:__imp_OutputDebugStringA
0x180003e91  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x180003e98  call    cs:__imp_OutputDebugStringA
0x180003e9e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180003ea5  call    cs:__imp_OutputDebugStringA
0x180003eab  call    cs:__imp_DebugBreak
0x180003eb1  xor     eax, eax
0x180003eb3  add     rsp, 28h
0x180003eb7  retn
```
