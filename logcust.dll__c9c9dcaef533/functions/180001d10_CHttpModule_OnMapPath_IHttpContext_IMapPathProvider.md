# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180001d10`
- end: `0x180001d48`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d35`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d35`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d3b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d3b`

## string_xrefs

- `0x180001d21`: `CHttpModule::OnMapPath`

## pseudocode

```c
__int64 CHttpModule::OnMapPath()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnMapPath");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001d10  sub     rsp, 28h
0x180001d14  lea     rcx, OutputString; "This module subscribed to event "
0x180001d1b  call    cs:__imp_OutputDebugStringA
0x180001d21  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x180001d28  call    cs:__imp_OutputDebugStringA
0x180001d2e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001d35  call    cs:__imp_OutputDebugStringA
0x180001d3b  call    cs:__imp_DebugBreak
0x180001d41  xor     eax, eax
0x180001d43  add     rsp, 28h
0x180001d47  retn
```
