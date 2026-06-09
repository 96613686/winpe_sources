# __imp_load_GetUserProfileDirectoryW

- ea: `0x180001dfc`
- end: `0x180001e08`
- name: `__imp_load_GetUserProfileDirectoryW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001d7d`

## import_xrefs

- `USERENV!GetUserProfileDirectoryW` at `0x180001dfc`

## pseudocode

```c
__int64 load_GetUserProfileDirectoryW()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x180001dfc  lea     rax, __imp_GetUserProfileDirectoryW
0x180001e03  jmp     __tailMerge_userenv_dll
```
