# __scrt_dllmain_before_initialize_c

- ea: `0x180001670`
- end: `0x180001677`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800012b8`

## callees

- `0x1800017b0`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180001670  xor     ecx, ecx
0x180001672  jmp     __scrt_initialize_onexit_tables
```
