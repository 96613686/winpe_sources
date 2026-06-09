# __imp_load_NduOpenHandle

- ea: `0x18001c877`
- end: `0x18001c883`
- name: `__imp_load_NduOpenHandle`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c7c2`

## import_xrefs

- `NduProv!__imp_NduOpenHandle` at `0x18001c877`

## pseudocode

```c
__int64 load_NduOpenHandle()
{
  return _tailMerge_nduprov_dll();
}

```

## disassembly

```asm
0x18001c877  lea     rax, __imp_NduOpenHandle
0x18001c87e  jmp     __tailMerge_nduprov_dll
```
