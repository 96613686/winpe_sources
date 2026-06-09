# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x1800042a0`
- end: `0x1800042d8`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800042cb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800042cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800042ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800042b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800042c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800042ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800042b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800042c5`

## string_xrefs

- `0x1800042b1`: `CHttpModule::OnReadEntity`

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
0x1800042a0  sub     rsp, 28h
0x1800042a4  lea     rcx, OutputString; "This module subscribed to event "
0x1800042ab  call    cs:__imp_OutputDebugStringA
0x1800042b1  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x1800042b8  call    cs:__imp_OutputDebugStringA
0x1800042be  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800042c5  call    cs:__imp_OutputDebugStringA
0x1800042cb  call    cs:__imp_DebugBreak
0x1800042d1  xor     eax, eax
0x1800042d3  add     rsp, 28h
0x1800042d7  retn
```
