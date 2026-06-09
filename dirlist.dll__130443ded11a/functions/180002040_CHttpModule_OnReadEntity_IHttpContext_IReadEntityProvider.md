# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180002040`
- end: `0x180002078`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000206b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000206b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000204b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002058`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002065`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000204b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002058`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002065`

## string_xrefs

- `0x180002051`: `CHttpModule::OnReadEntity`

## pseudocode

```c
__int64 CHttpModule::OnReadEntity()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnReadEntity");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002040  sub     rsp, 28h
0x180002044  lea     rcx, OutputString; "This module subscribed to event "
0x18000204b  call    cs:__imp_OutputDebugStringA
0x180002051  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180002058  call    cs:__imp_OutputDebugStringA
0x18000205e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002065  call    cs:__imp_OutputDebugStringA
0x18000206b  call    cs:__imp_DebugBreak
0x180002071  xor     eax, eax
0x180002073  add     rsp, 28h
0x180002077  retn
```
