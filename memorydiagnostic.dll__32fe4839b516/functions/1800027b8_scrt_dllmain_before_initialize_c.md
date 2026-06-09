# __scrt_dllmain_before_initialize_c

- ea: `0x1800027b8`
- end: `0x1800027cd`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002388`

## callees

- `0x18000291c`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x1800027b8  sub     rsp, 28h
0x1800027bc  xor     ecx, ecx
0x1800027be  call    __scrt_initialize_onexit_tables
0x1800027c3  test    al, al
0x1800027c5  setnz   al
0x1800027c8  add     rsp, 28h
0x1800027cc  retn
```
