# __imp_load_CopyRect

- ea: `0x180003ff8`
- end: `0x180004004`
- name: `__imp_load_CopyRect`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003ddb`

## import_xrefs

- `USER32!CopyRect` at `0x180003ff8`

## pseudocode

```c
__int64 load_CopyRect()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x180003ff8  lea     rax, __imp_CopyRect
0x180003fff  jmp     __tailMerge_user32_dll
```
