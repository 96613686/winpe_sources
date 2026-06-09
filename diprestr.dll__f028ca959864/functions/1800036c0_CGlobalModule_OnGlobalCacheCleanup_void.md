# CGlobalModule::OnGlobalCacheCleanup(void)

- ea: `0x1800036c0`
- end: `0x1800036f8`
- name: `?OnGlobalCacheCleanup@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@XZ`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800036cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800036d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800036e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800036cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800036d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800036e5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800036eb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800036eb`

## string_xrefs

- `0x1800036d1`: `CGlobalModule::OnGlobalCacheCleanup`

## pseudocode

```c
__int64 CGlobalModule::OnGlobalCacheCleanup()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CGlobalModule::OnGlobalCacheCleanup");
  OutputDebugStringA(
    " but did not override the method in its CGlobalModule implementation.  Please check the method signature to make sur"
    "e it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800036c0  sub     rsp, 28h
0x1800036c4  lea     rcx, OutputString; "This module subscribed to event "
0x1800036cb  call    cs:__imp_OutputDebugStringA
0x1800036d1  lea     rcx, aCglobalmoduleO_10; "CGlobalModule::OnGlobalCacheCleanup"
0x1800036d8  call    cs:__imp_OutputDebugStringA
0x1800036de  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800036e5  call    cs:__imp_OutputDebugStringA
0x1800036eb  call    cs:__imp_DebugBreak
0x1800036f1  xor     eax, eax
0x1800036f3  add     rsp, 28h
0x1800036f7  retn
```
