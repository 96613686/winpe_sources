# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180007d70`
- end: `0x180007da8`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007d7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007d88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007d95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007d7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007d88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007d95`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180007d9b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180007d9b`

## string_xrefs

- `0x180007d81`: `CHttpModule::OnReadEntity`

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
0x180007d70  sub     rsp, 28h
0x180007d74  lea     rcx, OutputString; "This module subscribed to event "
0x180007d7b  call    cs:__imp_OutputDebugStringA
0x180007d81  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180007d88  call    cs:__imp_OutputDebugStringA
0x180007d8e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180007d95  call    cs:__imp_OutputDebugStringA
0x180007d9b  call    cs:__imp_DebugBreak
0x180007da1  xor     eax, eax
0x180007da3  add     rsp, 28h
0x180007da7  retn
```
