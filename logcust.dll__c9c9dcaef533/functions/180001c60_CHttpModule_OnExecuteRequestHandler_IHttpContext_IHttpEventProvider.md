# CHttpModule::OnExecuteRequestHandler(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001c60`
- end: `0x180001c98`
- name: `?OnExecuteRequestHandler@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c85`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c85`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001c8b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001c8b`

## pseudocode

```c
__int64 CHttpModule::OnExecuteRequestHandler()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnExecuteRequestHandler");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001c60  sub     rsp, 28h
0x180001c64  lea     rcx, OutputString; "This module subscribed to event "
0x180001c6b  call    cs:__imp_OutputDebugStringA
0x180001c71  lea     rcx, aChttpmoduleOne; "CHttpModule::OnExecuteRequestHandler"
0x180001c78  call    cs:__imp_OutputDebugStringA
0x180001c7e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001c85  call    cs:__imp_OutputDebugStringA
0x180001c8b  call    cs:__imp_DebugBreak
0x180001c91  xor     eax, eax
0x180001c93  add     rsp, 28h
0x180001c97  retn
```
