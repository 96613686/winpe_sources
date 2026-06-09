# CHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180003400`
- end: `0x180003438`
- name: `?OnAsyncCompletion@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000340b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003418`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003425`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000340b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003418`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003425`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000342b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000342b`

## string_xrefs

- `0x180003411`: `CHttpModule::OnAsyncCompletion`

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
0x180003400  sub     rsp, 28h
0x180003404  lea     rcx, OutputString; "This module subscribed to event "
0x18000340b  call    cs:__imp_OutputDebugStringA
0x180003411  lea     rcx, aChttpmoduleOna_1; "CHttpModule::OnAsyncCompletion"
0x180003418  call    cs:__imp_OutputDebugStringA
0x18000341e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180003425  call    cs:__imp_OutputDebugStringA
0x18000342b  call    cs:__imp_DebugBreak
0x180003431  xor     eax, eax
0x180003433  add     rsp, 28h
0x180003437  retn
```
