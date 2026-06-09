# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180008810`
- end: `0x180008848`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000883b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000883b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000881b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180008828`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180008835`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000881b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180008828`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180008835`

## string_xrefs

- `0x180008821`: `CHttpModule::OnReadEntity`

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
0x180008810  sub     rsp, 28h
0x180008814  lea     rcx, OutputString; "This module subscribed to event "
0x18000881b  call    cs:__imp_OutputDebugStringA
0x180008821  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180008828  call    cs:__imp_OutputDebugStringA
0x18000882e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180008835  call    cs:__imp_OutputDebugStringA
0x18000883b  call    cs:__imp_DebugBreak
0x180008841  xor     eax, eax
0x180008843  add     rsp, 28h
0x180008847  retn
```
