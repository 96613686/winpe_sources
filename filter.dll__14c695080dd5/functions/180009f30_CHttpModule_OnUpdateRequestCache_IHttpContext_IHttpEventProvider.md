# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180009f30`
- end: `0x180009f68`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180009f5b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180009f5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009f3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009f48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009f55`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009f3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009f48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009f55`

## string_xrefs

- `0x180009f41`: `CHttpModule::OnUpdateRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnUpdateRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnUpdateRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180009f30  sub     rsp, 28h
0x180009f34  lea     rcx, OutputString; "This module subscribed to event "
0x180009f3b  call    cs:__imp_OutputDebugStringA
0x180009f41  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x180009f48  call    cs:__imp_OutputDebugStringA
0x180009f4e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180009f55  call    cs:__imp_OutputDebugStringA
0x180009f5b  call    cs:__imp_DebugBreak
0x180009f61  xor     eax, eax
0x180009f63  add     rsp, 28h
0x180009f67  retn
```
