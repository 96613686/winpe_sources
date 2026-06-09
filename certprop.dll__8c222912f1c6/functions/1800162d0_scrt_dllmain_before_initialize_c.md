# __scrt_dllmain_before_initialize_c

- ea: `0x1800162d0`
- end: `0x1800162d7`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015d78`

## callees

- `0x180016410`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x1800162d0  xor     ecx, ecx
0x1800162d2  jmp     __scrt_initialize_onexit_tables
```
