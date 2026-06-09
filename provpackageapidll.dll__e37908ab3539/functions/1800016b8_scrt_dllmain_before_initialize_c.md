# __scrt_dllmain_before_initialize_c

- ea: `0x1800016b8`
- end: `0x1800016bf`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800011f8`

## callees

- `0x1800017f8`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x1800016b8  xor     ecx, ecx
0x1800016ba  jmp     __scrt_initialize_onexit_tables
```
