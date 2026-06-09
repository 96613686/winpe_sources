# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x18000dab0`
- end: `0x18000dae8`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000dadb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000dadb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dabb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dac8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dad5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dabb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dac8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dad5`

## string_xrefs

- `0x18000dac1`: `CHttpModule::OnReadEntity`

## pseudocode

```c
__int64 CHttpModule::OnReadEntity()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnReadEntity");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x18000dab0  sub     rsp, 28h
0x18000dab4  lea     rcx, OutputString; "This module subscribed to event "
0x18000dabb  call    cs:__imp_OutputDebugStringA
0x18000dac1  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x18000dac8  call    cs:__imp_OutputDebugStringA
0x18000dace  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x18000dad5  call    cs:__imp_OutputDebugStringA
0x18000dadb  call    cs:__imp_DebugBreak
0x18000dae1  xor     eax, eax
0x18000dae3  add     rsp, 28h
0x18000dae7  retn
```
