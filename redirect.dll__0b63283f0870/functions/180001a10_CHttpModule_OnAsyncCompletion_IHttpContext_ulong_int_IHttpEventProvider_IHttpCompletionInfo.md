# CHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180001a10`
- end: `0x180001a48`
- name: `?OnAsyncCompletion@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a35`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a35`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001a3b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001a3b`

## string_xrefs

- `0x180001a21`: `CHttpModule::OnAsyncCompletion`

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
0x180001a10  sub     rsp, 28h
0x180001a14  lea     rcx, OutputString; "This module subscribed to event "
0x180001a1b  call    cs:__imp_OutputDebugStringA
0x180001a21  lea     rcx, aChttpmoduleOna_1; "CHttpModule::OnAsyncCompletion"
0x180001a28  call    cs:__imp_OutputDebugStringA
0x180001a2e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001a35  call    cs:__imp_OutputDebugStringA
0x180001a3b  call    cs:__imp_DebugBreak
0x180001a41  xor     eax, eax
0x180001a43  add     rsp, 28h
0x180001a47  retn
```
