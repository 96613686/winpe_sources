# CHttpModule::OnPostEndRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001e30`
- end: `0x180001e68`
- name: `?OnPostEndRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001e3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001e48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001e55`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001e3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001e48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001e55`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001e5b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001e5b`

## pseudocode

```c
__int64 CHttpModule::OnPostEndRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostEndRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001e30  sub     rsp, 28h
0x180001e34  lea     rcx, OutputString; "This module subscribed to event "
0x180001e3b  call    cs:__imp_OutputDebugStringA
0x180001e41  lea     rcx, aChttpmoduleOnp_4; "CHttpModule::OnPostEndRequest"
0x180001e48  call    cs:__imp_OutputDebugStringA
0x180001e4e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001e55  call    cs:__imp_OutputDebugStringA
0x180001e5b  call    cs:__imp_DebugBreak
0x180001e61  xor     eax, eax
0x180001e63  add     rsp, 28h
0x180001e67  retn
```
