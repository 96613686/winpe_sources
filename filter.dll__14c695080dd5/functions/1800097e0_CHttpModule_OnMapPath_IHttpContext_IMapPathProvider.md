# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x1800097e0`
- end: `0x180009818`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000980b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000980b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800097eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800097f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009805`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800097eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800097f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009805`

## string_xrefs

- `0x1800097f1`: `CHttpModule::OnMapPath`

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
0x1800097e0  sub     rsp, 28h
0x1800097e4  lea     rcx, OutputString; "This module subscribed to event "
0x1800097eb  call    cs:__imp_OutputDebugStringA
0x1800097f1  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x1800097f8  call    cs:__imp_OutputDebugStringA
0x1800097fe  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180009805  call    cs:__imp_OutputDebugStringA
0x18000980b  call    cs:__imp_DebugBreak
0x180009811  xor     eax, eax
0x180009813  add     rsp, 28h
0x180009817  retn
```
