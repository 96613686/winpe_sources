# __scrt_dllmain_before_initialize_c

- ea: `0x18001e270`
- end: `0x18001e277`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001dea8`

## callees

- `0x18001e3b0`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x18001e270  xor     ecx, ecx
0x18001e272  jmp     __scrt_initialize_onexit_tables
```
