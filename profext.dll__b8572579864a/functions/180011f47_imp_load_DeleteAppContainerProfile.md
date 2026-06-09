# __imp_load_DeleteAppContainerProfile

- ea: `0x180011f47`
- end: `0x180011f53`
- name: `__imp_load_DeleteAppContainerProfile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011e86`

## import_xrefs

- `USERENV!DeleteAppContainerProfile` at `0x180011f47`

## pseudocode

```c
__int64 load_DeleteAppContainerProfile()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x180011f47  lea     rax, __imp_DeleteAppContainerProfile
0x180011f4e  jmp     __tailMerge_userenv_dll
```
