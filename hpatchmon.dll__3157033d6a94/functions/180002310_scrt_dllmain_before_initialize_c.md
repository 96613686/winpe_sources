# __scrt_dllmain_before_initialize_c

- ea: `0x180002310`
- end: `0x180002317`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001f58`

## callees

- `0x180002450`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180002310  xor     ecx, ecx
0x180002312  jmp     __scrt_initialize_onexit_tables
```
