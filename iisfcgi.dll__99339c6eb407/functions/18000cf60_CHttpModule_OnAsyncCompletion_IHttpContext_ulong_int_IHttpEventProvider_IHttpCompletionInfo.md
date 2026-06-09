# CHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x18000cf60`
- end: `0x18000cf98`
- name: `?OnAsyncCompletion@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000cf8b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000cf8b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cf6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cf78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cf85`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cf6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cf78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cf85`

## string_xrefs

- `0x18000cf71`: `CHttpModule::OnAsyncCompletion`

## pseudocode

```c
__int64 CHttpModule::OnAsyncCompletion()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnAsyncCompletion");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x18000cf60  sub     rsp, 28h
0x18000cf64  lea     rcx, OutputString; "This module subscribed to event "
0x18000cf6b  call    cs:__imp_OutputDebugStringA
0x18000cf71  lea     rcx, aChttpmoduleOna_1; "CHttpModule::OnAsyncCompletion"
0x18000cf78  call    cs:__imp_OutputDebugStringA
0x18000cf7e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x18000cf85  call    cs:__imp_OutputDebugStringA
0x18000cf8b  call    cs:__imp_DebugBreak
0x18000cf91  xor     eax, eax
0x18000cf93  add     rsp, 28h
0x18000cf97  retn
```
