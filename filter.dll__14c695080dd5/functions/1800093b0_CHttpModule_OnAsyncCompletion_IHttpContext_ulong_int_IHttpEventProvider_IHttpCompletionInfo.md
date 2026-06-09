# CHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800093b0`
- end: `0x1800093e8`
- name: `?OnAsyncCompletion@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800093db`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800093db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800093bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800093c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800093d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800093bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800093c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800093d5`

## string_xrefs

- `0x1800093c1`: `CHttpModule::OnAsyncCompletion`

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
0x1800093b0  sub     rsp, 28h
0x1800093b4  lea     rcx, OutputString; "This module subscribed to event "
0x1800093bb  call    cs:__imp_OutputDebugStringA
0x1800093c1  lea     rcx, aChttpmoduleOna_1; "CHttpModule::OnAsyncCompletion"
0x1800093c8  call    cs:__imp_OutputDebugStringA
0x1800093ce  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x1800093d5  call    cs:__imp_OutputDebugStringA
0x1800093db  call    cs:__imp_DebugBreak
0x1800093e1  xor     eax, eax
0x1800093e3  add     rsp, 28h
0x1800093e7  retn
```
