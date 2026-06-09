# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180001cb0`
- end: `0x180001ce8`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cc8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cd5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cc8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cd5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001cdb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001cdb`

## string_xrefs

- `0x180001cc1`: `CHttpModule::OnMapPath`

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
0x180001cb0  sub     rsp, 28h
0x180001cb4  lea     rcx, OutputString; "This module subscribed to event "
0x180001cbb  call    cs:__imp_OutputDebugStringA
0x180001cc1  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x180001cc8  call    cs:__imp_OutputDebugStringA
0x180001cce  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001cd5  call    cs:__imp_OutputDebugStringA
0x180001cdb  call    cs:__imp_DebugBreak
0x180001ce1  xor     eax, eax
0x180001ce3  add     rsp, 28h
0x180001ce7  retn
```
