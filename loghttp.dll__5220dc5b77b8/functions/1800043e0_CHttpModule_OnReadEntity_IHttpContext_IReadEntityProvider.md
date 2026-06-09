# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x1800043e0`
- end: `0x180004418`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800043eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800043f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004405`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800043eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800043f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004405`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000440b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000440b`

## string_xrefs

- `0x1800043f1`: `CHttpModule::OnReadEntity`

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
0x1800043e0  sub     rsp, 28h
0x1800043e4  lea     rcx, OutputString; "This module subscribed to event "
0x1800043eb  call    cs:__imp_OutputDebugStringA
0x1800043f1  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x1800043f8  call    cs:__imp_OutputDebugStringA
0x1800043fe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180004405  call    cs:__imp_OutputDebugStringA
0x18000440b  call    cs:__imp_DebugBreak
0x180004411  xor     eax, eax
0x180004413  add     rsp, 28h
0x180004417  retn
```
