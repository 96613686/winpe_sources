# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800021d0`
- end: `0x180002208`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021f5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800021fb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800021fb`

## string_xrefs

- `0x1800021e1`: `CHttpModule::OnUpdateRequestCache`

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
0x1800021d0  sub     rsp, 28h
0x1800021d4  lea     rcx, OutputString; "This module subscribed to event "
0x1800021db  call    cs:__imp_OutputDebugStringA
0x1800021e1  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x1800021e8  call    cs:__imp_OutputDebugStringA
0x1800021ee  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800021f5  call    cs:__imp_OutputDebugStringA
0x1800021fb  call    cs:__imp_DebugBreak
0x180002201  xor     eax, eax
0x180002203  add     rsp, 28h
0x180002207  retn
```
