# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180002570`
- end: `0x1800025a8`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000257b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002588`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002595`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000257b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002588`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002595`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000259b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000259b`

## string_xrefs

- `0x180002581`: `CHttpModule::OnMapPath`

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
0x180002570  sub     rsp, 28h
0x180002574  lea     rcx, aThisModuleSubs; "This module subscribed to event "
0x18000257b  call    cs:__imp_OutputDebugStringA
0x180002581  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x180002588  call    cs:__imp_OutputDebugStringA
0x18000258e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180002595  call    cs:__imp_OutputDebugStringA
0x18000259b  call    cs:__imp_DebugBreak
0x1800025a1  xor     eax, eax
0x1800025a3  add     rsp, 28h
0x1800025a7  retn
```
