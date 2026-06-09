# __scrt_dllmain_before_initialize_c

- ea: `0x180003c38`
- end: `0x180003c3f`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003778`

## callees

- `0x180003d78`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180003c38  xor     ecx, ecx
0x180003c3a  jmp     __scrt_initialize_onexit_tables
```
