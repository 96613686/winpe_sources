# __imp_load_CommandLineToArgvW

- ea: `0x140010ba1`
- end: `0x140010bad`
- name: `__imp_load_CommandLineToArgvW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140010b10`

## import_xrefs

- `SHELL32!CommandLineToArgvW` at `0x140010ba1`

## pseudocode

```c
__int64 load_CommandLineToArgvW()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x140010ba1  lea     rax, __imp_CommandLineToArgvW
0x140010ba8  jmp     __tailMerge_shell32_dll
```
