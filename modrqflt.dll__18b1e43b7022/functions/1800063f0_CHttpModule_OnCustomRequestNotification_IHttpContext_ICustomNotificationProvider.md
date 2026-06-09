# CHttpModule::OnCustomRequestNotification(IHttpContext *,ICustomNotificationProvider *)

- ea: `0x1800063f0`
- end: `0x180006428`
- name: `?OnCustomRequestNotification@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVICustomNotificationProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000641b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000641b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800063fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006408`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006415`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800063fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006408`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006415`

## pseudocode

```c
__int64 CHttpModule::OnCustomRequestNotification()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnCustomRequestNotification");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800063f0  sub     rsp, 28h
0x1800063f4  lea     rcx, OutputString; "This module subscribed to event "
0x1800063fb  call    cs:__imp_OutputDebugStringA
0x180006401  lea     rcx, aChttpmoduleOnc; "CHttpModule::OnCustomRequestNotificatio"...
0x180006408  call    cs:__imp_OutputDebugStringA
0x18000640e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180006415  call    cs:__imp_OutputDebugStringA
0x18000641b  call    cs:__imp_DebugBreak
0x180006421  xor     eax, eax
0x180006423  add     rsp, 28h
0x180006427  retn
```
