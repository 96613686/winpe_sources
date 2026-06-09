# CHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180007630`
- end: `0x180007668`
- name: `?OnAsyncCompletion@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000763b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007648`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007655`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000763b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007648`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007655`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000765b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000765b`

## string_xrefs

- `0x180007641`: `CHttpModule::OnAsyncCompletion`

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
0x180007630  sub     rsp, 28h
0x180007634  lea     rcx, OutputString; "This module subscribed to event "
0x18000763b  call    cs:__imp_OutputDebugStringA
0x180007641  lea     rcx, aChttpmoduleOna_1; "CHttpModule::OnAsyncCompletion"
0x180007648  call    cs:__imp_OutputDebugStringA
0x18000764e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180007655  call    cs:__imp_OutputDebugStringA
0x18000765b  call    cs:__imp_DebugBreak
0x180007661  xor     eax, eax
0x180007663  add     rsp, 28h
0x180007667  retn
```
