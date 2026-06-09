# __scrt_dllmain_before_initialize_c

- ea: `0x180001fcc`
- end: `0x180001fd3`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001bd8`

## callees

- `0x18000210c`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180001fcc  xor     ecx, ecx
0x180001fce  jmp     __scrt_initialize_onexit_tables
```
