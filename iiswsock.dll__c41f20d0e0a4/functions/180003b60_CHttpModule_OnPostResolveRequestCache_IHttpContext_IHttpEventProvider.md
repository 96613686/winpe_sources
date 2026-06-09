# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003b60`
- end: `0x180003b98`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003b8b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003b8b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003b6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003b78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003b85`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003b6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003b78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003b85`

## string_xrefs

- `0x180003b71`: `CHttpModule::OnPostResolveRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnPostResolveRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostResolveRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180003b60  sub     rsp, 28h
0x180003b64  lea     rcx, OutputString; "This module subscribed to event "
0x180003b6b  call    cs:__imp_OutputDebugStringA
0x180003b71  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x180003b78  call    cs:__imp_OutputDebugStringA
0x180003b7e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003b85  call    cs:__imp_OutputDebugStringA
0x180003b8b  call    cs:__imp_DebugBreak
0x180003b91  xor     eax, eax
0x180003b93  add     rsp, 28h
0x180003b97  retn
```
