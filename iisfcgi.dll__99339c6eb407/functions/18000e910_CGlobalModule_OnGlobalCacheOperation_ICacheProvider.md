# CGlobalModule::OnGlobalCacheOperation(ICacheProvider *)

- ea: `0x18000e910`
- end: `0x18000e948`
- name: `?OnGlobalCacheOperation@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICacheProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e93b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e93b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e91b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e928`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e935`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e91b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e928`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e935`

## string_xrefs

- `0x18000e921`: `CGlobalModule::OnGlobalCacheOperation`

## pseudocode

```c
__int64 CGlobalModule::OnGlobalCacheOperation()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CGlobalModule::OnGlobalCacheOperation");
  OutputDebugStringA(
    " but did not override the method in its CGlobalModule implementation.  Please check the method signature to make sur"
    "e it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x18000e910  sub     rsp, 28h
0x18000e914  lea     rcx, OutputString; "This module subscribed to event "
0x18000e91b  call    cs:__imp_OutputDebugStringA
0x18000e921  lea     rcx, aCglobalmoduleO_6; "CGlobalModule::OnGlobalCacheOperation"
0x18000e928  call    cs:__imp_OutputDebugStringA
0x18000e92e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x18000e935  call    cs:__imp_OutputDebugStringA
0x18000e93b  call    cs:__imp_DebugBreak
0x18000e941  xor     eax, eax
0x18000e943  add     rsp, 28h
0x18000e947  retn
```
