# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x18000dbb0`
- end: `0x18000dbe8`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000dbdb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000dbdb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dbbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dbc8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dbd5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dbbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dbc8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dbd5`

## string_xrefs

- `0x18000dbc1`: `CHttpModule::OnUpdateRequestCache`

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
0x18000dbb0  sub     rsp, 28h
0x18000dbb4  lea     rcx, OutputString; "This module subscribed to event "
0x18000dbbb  call    cs:__imp_OutputDebugStringA
0x18000dbc1  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x18000dbc8  call    cs:__imp_OutputDebugStringA
0x18000dbce  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x18000dbd5  call    cs:__imp_OutputDebugStringA
0x18000dbdb  call    cs:__imp_DebugBreak
0x18000dbe1  xor     eax, eax
0x18000dbe3  add     rsp, 28h
0x18000dbe7  retn
```
