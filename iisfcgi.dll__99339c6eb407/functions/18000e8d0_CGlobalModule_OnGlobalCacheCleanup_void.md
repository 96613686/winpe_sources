# CGlobalModule::OnGlobalCacheCleanup(void)

- ea: `0x18000e8d0`
- end: `0x18000e908`
- name: `?OnGlobalCacheCleanup@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@XZ`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e8fb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e8fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e8db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e8e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e8f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e8db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e8e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e8f5`

## string_xrefs

- `0x18000e8e1`: `CGlobalModule::OnGlobalCacheCleanup`

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
0x18000e8d0  sub     rsp, 28h
0x18000e8d4  lea     rcx, OutputString; "This module subscribed to event "
0x18000e8db  call    cs:__imp_OutputDebugStringA
0x18000e8e1  lea     rcx, aCglobalmoduleO_9; "CGlobalModule::OnGlobalCacheCleanup"
0x18000e8e8  call    cs:__imp_OutputDebugStringA
0x18000e8ee  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x18000e8f5  call    cs:__imp_OutputDebugStringA
0x18000e8fb  call    cs:__imp_DebugBreak
0x18000e901  xor     eax, eax
0x18000e903  add     rsp, 28h
0x18000e907  retn
```
