# CHttpModule::OnPostUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001fa0`
- end: `0x180001fd8`
- name: `?OnPostUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001fab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001fb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001fc5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001fab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001fb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001fc5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001fcb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001fcb`

## string_xrefs

- `0x180001fb1`: `CHttpModule::OnPostUpdateRequestCache`

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
0x180001fa0  sub     rsp, 28h
0x180001fa4  lea     rcx, OutputString; "This module subscribed to event "
0x180001fab  call    cs:__imp_OutputDebugStringA
0x180001fb1  lea     rcx, aChttpmoduleOnp; "CHttpModule::OnPostUpdateRequestCache"
0x180001fb8  call    cs:__imp_OutputDebugStringA
0x180001fbe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001fc5  call    cs:__imp_OutputDebugStringA
0x180001fcb  call    cs:__imp_DebugBreak
0x180001fd1  xor     eax, eax
0x180001fd3  add     rsp, 28h
0x180001fd7  retn
```
