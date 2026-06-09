# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180002a50`
- end: `0x180002a88`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002a5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002a68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002a75`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002a5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002a68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002a75`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002a7b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002a7b`

## string_xrefs

- `0x180002a61`: `CHttpModule::OnReadEntity`

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
0x180002a50  sub     rsp, 28h
0x180002a54  lea     rcx, aThisModuleSubs; "This module subscribed to event "
0x180002a5b  call    cs:__imp_OutputDebugStringA
0x180002a61  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180002a68  call    cs:__imp_OutputDebugStringA
0x180002a6e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180002a75  call    cs:__imp_OutputDebugStringA
0x180002a7b  call    cs:__imp_DebugBreak
0x180002a81  xor     eax, eax
0x180002a83  add     rsp, 28h
0x180002a87  retn
```
