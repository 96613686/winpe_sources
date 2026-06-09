# __scrt_dllmain_before_initialize_c

- ea: `0x180004a68`
- end: `0x180004a6f`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800045a8`

## callees

- `0x180004ba8`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180004a68  xor     ecx, ecx
0x180004a6a  jmp     __scrt_initialize_onexit_tables
```
