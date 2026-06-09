# CHttpModule::OnPostUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002050`
- end: `0x180002088`
- name: `?OnPostUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000205b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002068`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002075`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000205b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002068`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002075`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000207b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000207b`

## string_xrefs

- `0x180002061`: `CHttpModule::OnPostUpdateRequestCache`

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
0x180002050  sub     rsp, 28h
0x180002054  lea     rcx, OutputString; "This module subscribed to event "
0x18000205b  call    cs:__imp_OutputDebugStringA
0x180002061  lea     rcx, aChttpmoduleOnp; "CHttpModule::OnPostUpdateRequestCache"
0x180002068  call    cs:__imp_OutputDebugStringA
0x18000206e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002075  call    cs:__imp_OutputDebugStringA
0x18000207b  call    cs:__imp_DebugBreak
0x180002081  xor     eax, eax
0x180002083  add     rsp, 28h
0x180002087  retn
```
