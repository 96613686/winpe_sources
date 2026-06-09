# __imp_load_DeleteProfileW

- ea: `0x18000327f`
- end: `0x18000328b`
- name: `__imp_load_DeleteProfileW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003200`

## import_xrefs

- `USERENV!DeleteProfileW` at `0x18000327f`

## pseudocode

```c
__int64 load_DeleteProfileW()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x18000327f  lea     rax, __imp_DeleteProfileW
0x180003286  jmp     __tailMerge_userenv_dll
```
