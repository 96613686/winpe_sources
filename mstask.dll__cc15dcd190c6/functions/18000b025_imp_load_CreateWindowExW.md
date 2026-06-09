# __imp_load_CreateWindowExW

- ea: `0x18000b025`
- end: `0x18000b031`
- name: `__imp_load_CreateWindowExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ae36`

## import_xrefs

- `USER32!CreateWindowExW` at `0x18000b025`

## pseudocode

```c
__int64 load_CreateWindowExW()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x18000b025  lea     rax, __imp_CreateWindowExW
0x18000b02c  jmp     __tailMerge_user32_dll
```
