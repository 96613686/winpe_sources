# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180007930`
- end: `0x180007968`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000793b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007948`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007955`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000793b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007948`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007955`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000795b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000795b`

## string_xrefs

- `0x180007941`: `CHttpModule::OnMapPath`

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
0x180007930  sub     rsp, 28h
0x180007934  lea     rcx, OutputString; "This module subscribed to event "
0x18000793b  call    cs:__imp_OutputDebugStringA
0x180007941  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x180007948  call    cs:__imp_OutputDebugStringA
0x18000794e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180007955  call    cs:__imp_OutputDebugStringA
0x18000795b  call    cs:__imp_DebugBreak
0x180007961  xor     eax, eax
0x180007963  add     rsp, 28h
0x180007967  retn
```
