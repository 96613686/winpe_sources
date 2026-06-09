# CHttpModule::OnPostAcquireRequestState(IHttpContext *,IHttpEventProvider *)

- ea: `0x180005820`
- end: `0x180005858`
- name: `?OnPostAcquireRequestState@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000584b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000584b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000582b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005838`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005845`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000582b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005838`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005845`

## pseudocode

```c
__int64 CHttpModule::OnPostAcquireRequestState()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostAcquireRequestState");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180005820  sub     rsp, 28h
0x180005824  lea     rcx, OutputString; "This module subscribed to event "
0x18000582b  call    cs:__imp_OutputDebugStringA
0x180005831  lea     rcx, aChttpmoduleOnp_7; "CHttpModule::OnPostAcquireRequestState"
0x180005838  call    cs:__imp_OutputDebugStringA
0x18000583e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180005845  call    cs:__imp_OutputDebugStringA
0x18000584b  call    cs:__imp_DebugBreak
0x180005851  xor     eax, eax
0x180005853  add     rsp, 28h
0x180005857  retn
```
