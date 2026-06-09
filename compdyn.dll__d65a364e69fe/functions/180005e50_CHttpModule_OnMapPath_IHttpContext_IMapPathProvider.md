# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180005e50`
- end: `0x180005e88`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180005e7b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180005e7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005e5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005e68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005e75`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005e5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005e68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005e75`

## string_xrefs

- `0x180005e61`: `CHttpModule::OnMapPath`

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
0x180005e50  sub     rsp, 28h
0x180005e54  lea     rcx, OutputString; "This module subscribed to event "
0x180005e5b  call    cs:__imp_OutputDebugStringA
0x180005e61  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x180005e68  call    cs:__imp_OutputDebugStringA
0x180005e6e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180005e75  call    cs:__imp_OutputDebugStringA
0x180005e7b  call    cs:__imp_DebugBreak
0x180005e81  xor     eax, eax
0x180005e83  add     rsp, 28h
0x180005e87  retn
```
