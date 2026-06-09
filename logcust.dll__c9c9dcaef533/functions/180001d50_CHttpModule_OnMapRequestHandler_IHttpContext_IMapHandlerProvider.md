# CHttpModule::OnMapRequestHandler(IHttpContext *,IMapHandlerProvider *)

- ea: `0x180001d50`
- end: `0x180001d88`
- name: `?OnMapRequestHandler@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapHandlerProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d75`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d75`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d7b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d7b`

## pseudocode

```c
__int64 CHttpModule::OnMapRequestHandler()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnMapRequestHandler");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001d50  sub     rsp, 28h
0x180001d54  lea     rcx, OutputString; "This module subscribed to event "
0x180001d5b  call    cs:__imp_OutputDebugStringA
0x180001d61  lea     rcx, aChttpmoduleOnm; "CHttpModule::OnMapRequestHandler"
0x180001d68  call    cs:__imp_OutputDebugStringA
0x180001d6e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001d75  call    cs:__imp_OutputDebugStringA
0x180001d7b  call    cs:__imp_DebugBreak
0x180001d81  xor     eax, eax
0x180001d83  add     rsp, 28h
0x180001d87  retn
```
