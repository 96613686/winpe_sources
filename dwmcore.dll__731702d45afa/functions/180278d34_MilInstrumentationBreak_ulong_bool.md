# MilInstrumentationBreak(ulong,bool)

- ea: `0x180278d34`
- end: `0x180278de9`
- name: `?MilInstrumentationBreak@@YAXK_N@Z`
- size: `181`
- prototype: `void(unsigned int, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800516dc`

## callees

- `0x1801eb014`
- `0x180202b80`
- `0x1802169d4`
- `0x180278d34`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180278d8a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180278d8a`
- `ntdll!NtQuerySystemInformation` at `0x180278dad`
- `ntdll!NtQuerySystemInformation` at `0x180278dad`

## string_xrefs

- `0x180278dcc`: `onecoreuap\windows\dwm\common\util\utillib\debugbreak.cpp`

## pseudocode

```c

```
