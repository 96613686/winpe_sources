# __scrt_dllmain_before_initialize_c

- ea: `0x180001f1c`
- end: `0x180001f23`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001b48`

## callees

- `0x18000205c`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180001f1c  xor     ecx, ecx
0x180001f1e  jmp     __scrt_initialize_onexit_tables
```
