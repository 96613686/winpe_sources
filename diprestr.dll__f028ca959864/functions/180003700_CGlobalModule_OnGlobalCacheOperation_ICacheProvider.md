# CGlobalModule::OnGlobalCacheOperation(ICacheProvider *)

- ea: `0x180003700`
- end: `0x180003738`
- name: `?OnGlobalCacheOperation@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICacheProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000370b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003718`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003725`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000370b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003718`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003725`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000372b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000372b`

## string_xrefs

- `0x180003711`: `CGlobalModule::OnGlobalCacheOperation`

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
0x180003700  sub     rsp, 28h
0x180003704  lea     rcx, OutputString; "This module subscribed to event "
0x18000370b  call    cs:__imp_OutputDebugStringA
0x180003711  lea     rcx, aCglobalmoduleO_7; "CGlobalModule::OnGlobalCacheOperation"
0x180003718  call    cs:__imp_OutputDebugStringA
0x18000371e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003725  call    cs:__imp_OutputDebugStringA
0x18000372b  call    cs:__imp_DebugBreak
0x180003731  xor     eax, eax
0x180003733  add     rsp, 28h
0x180003737  retn
```
