# __scrt_dllmain_before_initialize_c

- ea: `0x180001afc`
- end: `0x180001b03`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001738`

## callees

- `0x180001c3c`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180001afc  xor     ecx, ecx
0x180001afe  jmp     __scrt_initialize_onexit_tables
```
