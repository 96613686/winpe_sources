# __imp_load_CreateEnvironmentBlock

- ea: `0x180001f53`
- end: `0x180001f5f`
- name: `__imp_load_CreateEnvironmentBlock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001e9e`

## import_xrefs

- `USERENV!CreateEnvironmentBlock` at `0x180001f53`

## pseudocode

```c
__int64 load_CreateEnvironmentBlock()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x180001f53  lea     rax, __imp_CreateEnvironmentBlock
0x180001f5a  jmp     __tailMerge_userenv_dll
```
