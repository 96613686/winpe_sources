# __scrt_dllmain_before_initialize_c

- ea: `0x18000d140`
- end: `0x18000d147`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d4d8`

## callees

- `0x18000d280`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x18000d140  xor     ecx, ecx
0x18000d142  jmp     __scrt_initialize_onexit_tables
```
