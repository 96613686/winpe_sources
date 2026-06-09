# ___scrt_dllmain_before_initialize_c

- ea: `0x10012d06`
- end: `0x10012d0f`
- name: `___scrt_dllmain_before_initialize_c`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1001280b`

## callees

- `0x10012e06`

## pseudocode

```c
int __scrt_dllmain_before_initialize_c()
{
  return __scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x10012d06  push    0
0x10012d08  call    ___scrt_initialize_onexit_tables
0x10012d0d  pop     ecx
0x10012d0e  retn
```
