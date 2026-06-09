# __imp_load_CreateDUIWrapper

- ea: `0x180058544`
- end: `0x180058550`
- name: `__imp_load_CreateDUIWrapper`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800583ff`

## import_xrefs

- `DUI70!CreateDUIWrapper` at `0x180058544`

## pseudocode

```c
__int64 load_CreateDUIWrapper()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180058544  lea     rax, __imp_CreateDUIWrapper
0x18005854b  jmp     __tailMerge_dui70_dll
```
