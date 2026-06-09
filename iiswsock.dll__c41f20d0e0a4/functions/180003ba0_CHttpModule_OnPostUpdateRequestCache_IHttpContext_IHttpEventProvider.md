# CHttpModule::OnPostUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003ba0`
- end: `0x180003bd8`
- name: `?OnPostUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003bcb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003bcb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003bab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003bb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003bc5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003bab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003bb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003bc5`

## string_xrefs

- `0x180003bb1`: `CHttpModule::OnPostUpdateRequestCache`

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
0x180003ba0  sub     rsp, 28h
0x180003ba4  lea     rcx, OutputString; "This module subscribed to event "
0x180003bab  call    cs:__imp_OutputDebugStringA
0x180003bb1  lea     rcx, aChttpmoduleOnp; "CHttpModule::OnPostUpdateRequestCache"
0x180003bb8  call    cs:__imp_OutputDebugStringA
0x180003bbe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003bc5  call    cs:__imp_OutputDebugStringA
0x180003bcb  call    cs:__imp_DebugBreak
0x180003bd1  xor     eax, eax
0x180003bd3  add     rsp, 28h
0x180003bd7  retn
```
