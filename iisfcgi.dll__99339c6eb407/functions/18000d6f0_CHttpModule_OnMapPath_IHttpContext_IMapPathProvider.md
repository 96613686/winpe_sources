# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x18000d6f0`
- end: `0x18000d728`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d71b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d71b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d6fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d708`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d715`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d6fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d708`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d715`

## string_xrefs

- `0x18000d701`: `CHttpModule::OnMapPath`

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
0x18000d6f0  sub     rsp, 28h
0x18000d6f4  lea     rcx, OutputString; "This module subscribed to event "
0x18000d6fb  call    cs:__imp_OutputDebugStringA
0x18000d701  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x18000d708  call    cs:__imp_OutputDebugStringA
0x18000d70e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x18000d715  call    cs:__imp_OutputDebugStringA
0x18000d71b  call    cs:__imp_DebugBreak
0x18000d721  xor     eax, eax
0x18000d723  add     rsp, 28h
0x18000d727  retn
```
