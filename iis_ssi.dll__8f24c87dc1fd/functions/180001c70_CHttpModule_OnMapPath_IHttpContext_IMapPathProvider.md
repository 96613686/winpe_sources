# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180001c70`
- end: `0x180001ca8`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001c9b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001c9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c95`

## string_xrefs

- `0x180001c81`: `CHttpModule::OnMapPath`

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
0x180001c70  sub     rsp, 28h
0x180001c74  lea     rcx, OutputString; "This module subscribed to event "
0x180001c7b  call    cs:__imp_OutputDebugStringA
0x180001c81  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x180001c88  call    cs:__imp_OutputDebugStringA
0x180001c8e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001c95  call    cs:__imp_OutputDebugStringA
0x180001c9b  call    cs:__imp_DebugBreak
0x180001ca1  xor     eax, eax
0x180001ca3  add     rsp, 28h
0x180001ca7  retn
```
