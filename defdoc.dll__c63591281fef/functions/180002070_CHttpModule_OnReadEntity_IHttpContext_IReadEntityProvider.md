# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180002070`
- end: `0x1800020a8`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000207b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002088`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002095`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000207b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002088`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002095`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000209b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000209b`

## string_xrefs

- `0x180002081`: `CHttpModule::OnReadEntity`

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
0x180002070  sub     rsp, 28h
0x180002074  lea     rcx, OutputString; "This module subscribed to event "
0x18000207b  call    cs:__imp_OutputDebugStringA
0x180002081  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180002088  call    cs:__imp_OutputDebugStringA
0x18000208e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002095  call    cs:__imp_OutputDebugStringA
0x18000209b  call    cs:__imp_DebugBreak
0x1800020a1  xor     eax, eax
0x1800020a3  add     rsp, 28h
0x1800020a7  retn
```
