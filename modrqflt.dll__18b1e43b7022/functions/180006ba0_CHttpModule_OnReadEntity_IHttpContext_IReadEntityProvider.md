# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180006ba0`
- end: `0x180006bd8`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180006bcb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180006bcb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006bab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006bb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006bc5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006bab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006bb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006bc5`

## string_xrefs

- `0x180006bb1`: `CHttpModule::OnReadEntity`

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
0x180006ba0  sub     rsp, 28h
0x180006ba4  lea     rcx, OutputString; "This module subscribed to event "
0x180006bab  call    cs:__imp_OutputDebugStringA
0x180006bb1  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180006bb8  call    cs:__imp_OutputDebugStringA
0x180006bbe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180006bc5  call    cs:__imp_OutputDebugStringA
0x180006bcb  call    cs:__imp_DebugBreak
0x180006bd1  xor     eax, eax
0x180006bd3  add     rsp, 28h
0x180006bd7  retn
```
