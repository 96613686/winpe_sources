# CHttpModule::OnPostUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180006e30`
- end: `0x180006e68`
- name: `?OnPostUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180006e5b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180006e5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006e3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006e48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006e55`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006e3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006e48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006e55`

## string_xrefs

- `0x180006e41`: `CHttpModule::OnPostUpdateRequestCache`

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
0x180006e30  sub     rsp, 28h
0x180006e34  lea     rcx, OutputString; "This module subscribed to event "
0x180006e3b  call    cs:__imp_OutputDebugStringA
0x180006e41  lea     rcx, aChttpmoduleOnp; "CHttpModule::OnPostUpdateRequestCache"
0x180006e48  call    cs:__imp_OutputDebugStringA
0x180006e4e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180006e55  call    cs:__imp_OutputDebugStringA
0x180006e5b  call    cs:__imp_DebugBreak
0x180006e61  xor     eax, eax
0x180006e63  add     rsp, 28h
0x180006e67  retn
```
