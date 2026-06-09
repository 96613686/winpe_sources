# CGlobalModule::OnGlobalConfigurationChange(IGlobalConfigurationChangeProvider *)

- ea: `0x180003740`
- end: `0x180003778`
- name: `?OnGlobalConfigurationChange@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalConfigurationChangeProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000374b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003758`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003765`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000374b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003758`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003765`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000376b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000376b`

## string_xrefs

- `0x180003751`: `CGlobalModule::OnGlobalConfigurationChange`

## pseudocode

```c
__int64 CGlobalModule::OnGlobalConfigurationChange()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CGlobalModule::OnGlobalConfigurationChange");
  OutputDebugStringA(
    " but did not override the method in its CGlobalModule implementation.  Please check the method signature to make sur"
    "e it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180003740  sub     rsp, 28h
0x180003744  lea     rcx, OutputString; "This module subscribed to event "
0x18000374b  call    cs:__imp_OutputDebugStringA
0x180003751  lea     rcx, aCglobalmoduleO_13; "CGlobalModule::OnGlobalConfigurationCha"...
0x180003758  call    cs:__imp_OutputDebugStringA
0x18000375e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003765  call    cs:__imp_OutputDebugStringA
0x18000376b  call    cs:__imp_DebugBreak
0x180003771  xor     eax, eax
0x180003773  add     rsp, 28h
0x180003777  retn
```
