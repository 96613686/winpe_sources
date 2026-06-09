# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180006430`
- end: `0x180006468`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000645b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000645b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000643b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006448`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006455`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000643b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006448`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006455`

## string_xrefs

- `0x180006441`: `CHttpModule::OnUpdateRequestCache`

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
0x180006430  sub     rsp, 28h
0x180006434  lea     rcx, OutputString; "This module subscribed to event "
0x18000643b  call    cs:__imp_OutputDebugStringA
0x180006441  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x180006448  call    cs:__imp_OutputDebugStringA
0x18000644e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180006455  call    cs:__imp_OutputDebugStringA
0x18000645b  call    cs:__imp_DebugBreak
0x180006461  xor     eax, eax
0x180006463  add     rsp, 28h
0x180006467  retn
```
