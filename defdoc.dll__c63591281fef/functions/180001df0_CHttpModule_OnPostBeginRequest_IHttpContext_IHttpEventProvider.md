# CHttpModule::OnPostBeginRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001df0`
- end: `0x180001e28`
- name: `?OnPostBeginRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001dfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001e08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001e15`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001dfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001e08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001e15`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001e1b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001e1b`

## pseudocode

```c
__int64 CHttpModule::OnPostBeginRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostBeginRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001df0  sub     rsp, 28h
0x180001df4  lea     rcx, OutputString; "This module subscribed to event "
0x180001dfb  call    cs:__imp_OutputDebugStringA
0x180001e01  lea     rcx, aChttpmoduleOnp_10; "CHttpModule::OnPostBeginRequest"
0x180001e08  call    cs:__imp_OutputDebugStringA
0x180001e0e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001e15  call    cs:__imp_OutputDebugStringA
0x180001e1b  call    cs:__imp_DebugBreak
0x180001e21  xor     eax, eax
0x180001e23  add     rsp, 28h
0x180001e27  retn
```
