# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002120`
- end: `0x180002158`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000212b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002138`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002145`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000212b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002138`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002145`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000214b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000214b`

## string_xrefs

- `0x180002131`: `CHttpModule::OnUpdateRequestCache`

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
0x180002120  sub     rsp, 28h
0x180002124  lea     rcx, OutputString; "This module subscribed to event "
0x18000212b  call    cs:__imp_OutputDebugStringA
0x180002131  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x180002138  call    cs:__imp_OutputDebugStringA
0x18000213e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002145  call    cs:__imp_OutputDebugStringA
0x18000214b  call    cs:__imp_DebugBreak
0x180002151  xor     eax, eax
0x180002153  add     rsp, 28h
0x180002157  retn
```
