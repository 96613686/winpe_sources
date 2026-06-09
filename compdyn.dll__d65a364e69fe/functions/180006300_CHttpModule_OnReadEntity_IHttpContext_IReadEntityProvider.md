# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180006300`
- end: `0x180006338`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000632b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000632b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000630b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006318`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006325`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000630b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006318`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006325`

## string_xrefs

- `0x180006311`: `CHttpModule::OnReadEntity`

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
0x180006300  sub     rsp, 28h
0x180006304  lea     rcx, OutputString; "This module subscribed to event "
0x18000630b  call    cs:__imp_OutputDebugStringA
0x180006311  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180006318  call    cs:__imp_OutputDebugStringA
0x18000631e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180006325  call    cs:__imp_OutputDebugStringA
0x18000632b  call    cs:__imp_DebugBreak
0x180006331  xor     eax, eax
0x180006333  add     rsp, 28h
0x180006337  retn
```
