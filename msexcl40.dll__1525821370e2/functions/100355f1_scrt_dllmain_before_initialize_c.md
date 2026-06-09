# ___scrt_dllmain_before_initialize_c

- ea: `0x100355f1`
- end: `0x100355fa`
- name: `___scrt_dllmain_before_initialize_c`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100351cb`

## callees

- `0x100356f1`

## pseudocode

```c
int __scrt_dllmain_before_initialize_c()
{
  return __scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x100355f1  push    0
0x100355f3  call    ___scrt_initialize_onexit_tables
0x100355f8  pop     ecx
0x100355f9  retn
```
