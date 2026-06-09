# MilInstrumentationBreak(ulong,bool)

- ea: `0x180278d14`
- end: `0x180278dc9`
- name: `?MilInstrumentationBreak@@YAXK_N@Z`
- size: `181`
- prototype: `void(unsigned int, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004424c`

## callees

- `0x1801eb434`
- `0x180202b60`
- `0x1802169b4`
- `0x180278d14`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180278d6a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180278d6a`
- `ntdll!NtQuerySystemInformation` at `0x180278d8d`
- `ntdll!NtQuerySystemInformation` at `0x180278d8d`

## string_xrefs

- `0x180278dac`: `onecoreuap\windows\dwm\common\util\utillib\debugbreak.cpp`

## pseudocode

```c

```
