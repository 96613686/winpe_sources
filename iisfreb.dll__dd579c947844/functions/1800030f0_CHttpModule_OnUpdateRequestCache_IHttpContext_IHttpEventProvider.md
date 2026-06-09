# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800030f0`
- end: `0x180003128`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000311b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000311b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800030fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003108`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003115`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800030fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003108`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003115`

## string_xrefs

- `0x180003101`: `CHttpModule::OnUpdateRequestCache`

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
0x1800030f0  sub     rsp, 28h
0x1800030f4  lea     rcx, OutputString; "This module subscribed to event "
0x1800030fb  call    cs:__imp_OutputDebugStringA
0x180003101  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x180003108  call    cs:__imp_OutputDebugStringA
0x18000310e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180003115  call    cs:__imp_OutputDebugStringA
0x18000311b  call    cs:__imp_DebugBreak
0x180003121  xor     eax, eax
0x180003123  add     rsp, 28h
0x180003127  retn
```
