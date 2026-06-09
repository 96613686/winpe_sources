# __imp_load_CreateDirectoryJunctionsForUserProfile

- ea: `0x180011f05`
- end: `0x180011f11`
- name: `__imp_load_CreateDirectoryJunctionsForUserProfile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x180011e86`

## import_xrefs

- `USERENV!__imp_CreateDirectoryJunctionsForUserProfile` at `0x180011f05`

## pseudocode

```c
__int64 load_CreateDirectoryJunctionsForUserProfile()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x180011f05  lea     rax, __imp_CreateDirectoryJunctionsForUserProfile
0x180011f0c  jmp     __tailMerge_userenv_dll
```
