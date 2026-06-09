# __imp_load_PostThreadMessageA

- ea: `0x180001b5a`
- end: `0x180001b66`
- name: `__imp_load_PostThreadMessageA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001aa5`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x180001b5a`

## pseudocode

```c
__int64 load_PostThreadMessageA()
{
  return _tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll();
}

```

## disassembly

```asm
0x180001b5a  lea     rax, __imp_PostThreadMessageA
0x180001b61  jmp     __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll
```
