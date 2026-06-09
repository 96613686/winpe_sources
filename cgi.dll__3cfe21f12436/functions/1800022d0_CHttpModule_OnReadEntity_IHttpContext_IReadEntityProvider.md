# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x1800022d0`
- end: `0x180002308`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800022db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800022e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800022f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800022db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800022e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800022f5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800022fb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800022fb`

## string_xrefs

- `0x1800022e1`: `CHttpModule::OnReadEntity`

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
0x1800022d0  sub     rsp, 28h
0x1800022d4  lea     rcx, OutputString; "This module subscribed to event "
0x1800022db  call    cs:__imp_OutputDebugStringA
0x1800022e1  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x1800022e8  call    cs:__imp_OutputDebugStringA
0x1800022ee  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x1800022f5  call    cs:__imp_OutputDebugStringA
0x1800022fb  call    cs:__imp_DebugBreak
0x180002301  xor     eax, eax
0x180002303  add     rsp, 28h
0x180002307  retn
```
