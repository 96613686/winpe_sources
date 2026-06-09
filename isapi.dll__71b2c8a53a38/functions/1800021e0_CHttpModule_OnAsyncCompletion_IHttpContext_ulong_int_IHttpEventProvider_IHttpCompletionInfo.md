# CHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800021e0`
- end: `0x180002218`
- name: `?OnAsyncCompletion@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002205`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002205`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000220b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000220b`

## string_xrefs

- `0x1800021f1`: `CHttpModule::OnAsyncCompletion`

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
0x1800021e0  sub     rsp, 28h
0x1800021e4  lea     rcx, aThisModuleSubs; "This module subscribed to event "
0x1800021eb  call    cs:__imp_OutputDebugStringA
0x1800021f1  lea     rcx, aChttpmoduleOna_1; "CHttpModule::OnAsyncCompletion"
0x1800021f8  call    cs:__imp_OutputDebugStringA
0x1800021fe  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180002205  call    cs:__imp_OutputDebugStringA
0x18000220b  call    cs:__imp_DebugBreak
0x180002211  xor     eax, eax
0x180002213  add     rsp, 28h
0x180002217  retn
```
