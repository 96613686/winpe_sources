# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180003900`
- end: `0x180003938`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000390b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003918`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003925`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000390b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003918`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003925`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000392b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000392b`

## string_xrefs

- `0x180003911`: `CHttpModule::OnReadEntity`

## pseudocode

```c
__int64 CHttpModule::OnReadEntity()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnReadEntity");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180003900  sub     rsp, 28h
0x180003904  lea     rcx, OutputString; "This module subscribed to event "
0x18000390b  call    cs:__imp_OutputDebugStringA
0x180003911  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180003918  call    cs:__imp_OutputDebugStringA
0x18000391e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003925  call    cs:__imp_OutputDebugStringA
0x18000392b  call    cs:__imp_DebugBreak
0x180003931  xor     eax, eax
0x180003933  add     rsp, 28h
0x180003937  retn
```
