# __scrt_dllmain_before_initialize_c

- ea: `0x180001610`
- end: `0x180001617`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800010f8`

## callees

- `0x180001750`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180001610  xor     ecx, ecx
0x180001612  jmp     __scrt_initialize_onexit_tables
```
