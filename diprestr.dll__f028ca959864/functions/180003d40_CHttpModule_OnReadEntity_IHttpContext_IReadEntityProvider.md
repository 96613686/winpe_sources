# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180003d40`
- end: `0x180003d78`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003d4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003d58`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003d65`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003d4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003d58`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003d65`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003d6b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003d6b`

## string_xrefs

- `0x180003d51`: `CHttpModule::OnReadEntity`

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
0x180003d40  sub     rsp, 28h
0x180003d44  lea     rcx, OutputString; "This module subscribed to event "
0x180003d4b  call    cs:__imp_OutputDebugStringA
0x180003d51  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180003d58  call    cs:__imp_OutputDebugStringA
0x180003d5e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180003d65  call    cs:__imp_OutputDebugStringA
0x180003d6b  call    cs:__imp_DebugBreak
0x180003d71  xor     eax, eax
0x180003d73  add     rsp, 28h
0x180003d77  retn
```
