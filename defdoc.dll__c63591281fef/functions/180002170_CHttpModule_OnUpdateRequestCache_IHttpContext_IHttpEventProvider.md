# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002170`
- end: `0x1800021a8`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000217b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002188`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002195`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000217b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002188`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002195`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000219b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000219b`

## string_xrefs

- `0x180002181`: `CHttpModule::OnUpdateRequestCache`

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
0x180002170  sub     rsp, 28h
0x180002174  lea     rcx, OutputString; "This module subscribed to event "
0x18000217b  call    cs:__imp_OutputDebugStringA
0x180002181  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x180002188  call    cs:__imp_OutputDebugStringA
0x18000218e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002195  call    cs:__imp_OutputDebugStringA
0x18000219b  call    cs:__imp_DebugBreak
0x1800021a1  xor     eax, eax
0x1800021a3  add     rsp, 28h
0x1800021a7  retn
```
