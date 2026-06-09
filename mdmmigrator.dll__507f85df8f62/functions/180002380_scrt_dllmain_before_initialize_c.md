# __scrt_dllmain_before_initialize_c

- ea: `0x180002380`
- end: `0x180002387`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001fc8`

## callees

- `0x1800024c0`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180002380  xor     ecx, ecx
0x180002382  jmp     __scrt_initialize_onexit_tables
```
