# __imp_load_SCardAccessStartedEvent

- ea: `0x18000377d`
- end: `0x180003789`
- name: `__imp_load_SCardAccessStartedEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800036fe`

## import_xrefs

- `WinSCard!SCardAccessStartedEvent` at `0x18000377d`

## pseudocode

```c
__int64 load_SCardAccessStartedEvent()
{
  return _tailMerge_winscard_dll();
}

```

## disassembly

```asm
0x18000377d  lea     rax, __imp_SCardAccessStartedEvent
0x180003784  jmp     __tailMerge_winscard_dll
```
