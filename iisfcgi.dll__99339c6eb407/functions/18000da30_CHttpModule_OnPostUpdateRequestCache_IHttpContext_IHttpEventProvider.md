# CHttpModule::OnPostUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x18000da30`
- end: `0x18000da68`
- name: `?OnPostUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000da5b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000da5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000da3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000da48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000da55`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000da3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000da48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000da55`

## string_xrefs

- `0x18000da41`: `CHttpModule::OnPostUpdateRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnPostUpdateRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostUpdateRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x18000da30  sub     rsp, 28h
0x18000da34  lea     rcx, OutputString; "This module subscribed to event "
0x18000da3b  call    cs:__imp_OutputDebugStringA
0x18000da41  lea     rcx, aChttpmoduleOnp; "CHttpModule::OnPostUpdateRequestCache"
0x18000da48  call    cs:__imp_OutputDebugStringA
0x18000da4e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x18000da55  call    cs:__imp_OutputDebugStringA
0x18000da5b  call    cs:__imp_DebugBreak
0x18000da61  xor     eax, eax
0x18000da63  add     rsp, 28h
0x18000da67  retn
```
