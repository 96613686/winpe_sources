# __scrt_dllmain_before_initialize_c

- ea: `0x18000a184`
- end: `0x18000a18b`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009c98`

## callees

- `0x18000a2c4`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x18000a184  xor     ecx, ecx
0x18000a186  jmp     __scrt_initialize_onexit_tables
```
