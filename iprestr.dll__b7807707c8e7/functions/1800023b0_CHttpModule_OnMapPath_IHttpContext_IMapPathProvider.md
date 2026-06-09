# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x1800023b0`
- end: `0x1800023e8`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023d5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800023db`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800023db`

## string_xrefs

- `0x1800023c1`: `CHttpModule::OnMapPath`

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
0x1800023b0  sub     rsp, 28h
0x1800023b4  lea     rcx, OutputString; "This module subscribed to event "
0x1800023bb  call    cs:__imp_OutputDebugStringA
0x1800023c1  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x1800023c8  call    cs:__imp_OutputDebugStringA
0x1800023ce  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800023d5  call    cs:__imp_OutputDebugStringA
0x1800023db  call    cs:__imp_DebugBreak
0x1800023e1  xor     eax, eax
0x1800023e3  add     rsp, 28h
0x1800023e7  retn
```
