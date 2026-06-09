# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003a00`
- end: `0x180003a38`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003a0b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003a18`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003a25`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003a0b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003a18`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003a25`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003a2b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003a2b`

## string_xrefs

- `0x180003a11`: `CHttpModule::OnUpdateRequestCache`

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
0x180003a00  sub     rsp, 28h
0x180003a04  lea     rcx, OutputString; "This module subscribed to event "
0x180003a0b  call    cs:__imp_OutputDebugStringA
0x180003a11  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x180003a18  call    cs:__imp_OutputDebugStringA
0x180003a1e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003a25  call    cs:__imp_OutputDebugStringA
0x180003a2b  call    cs:__imp_DebugBreak
0x180003a31  xor     eax, eax
0x180003a33  add     rsp, 28h
0x180003a37  retn
```
