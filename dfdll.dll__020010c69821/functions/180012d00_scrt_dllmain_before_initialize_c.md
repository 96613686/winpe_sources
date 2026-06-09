# __scrt_dllmain_before_initialize_c

- ea: `0x180012d00`
- end: `0x180012d15`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012820`

## callees

- `0x180012e48`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x180012d00  sub     rsp, 28h
0x180012d04  xor     ecx, ecx
0x180012d06  call    __scrt_initialize_onexit_tables
0x180012d0b  test    al, al
0x180012d0d  setnz   al
0x180012d10  add     rsp, 28h
0x180012d14  retn
```
