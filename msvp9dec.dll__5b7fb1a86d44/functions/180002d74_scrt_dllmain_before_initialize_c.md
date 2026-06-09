# __scrt_dllmain_before_initialize_c

- ea: `0x180002d74`
- end: `0x180002d7b`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002998`

## callees

- `0x180002eb4`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180002d74  xor     ecx, ecx
0x180002d76  jmp     __scrt_initialize_onexit_tables
```
