# __scrt_dllmain_before_initialize_c

- ea: `0x1800050c0`
- end: `0x1800050c7`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004d08`

## callees

- `0x180005200`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x1800050c0  xor     ecx, ecx
0x1800050c2  jmp     __scrt_initialize_onexit_tables
```
