# __imp_load_DeleteProfileDirectory

- ea: `0x180011f7d`
- end: `0x180011f89`
- name: `__imp_load_DeleteProfileDirectory`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180011e86`

## import_xrefs

- `USERENV!__imp_DeleteProfileDirectory` at `0x180011f7d`

## pseudocode

```c
__int64 load_DeleteProfileDirectory()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x180011f7d  lea     rax, __imp_DeleteProfileDirectory
0x180011f84  jmp     __tailMerge_userenv_dll
```
