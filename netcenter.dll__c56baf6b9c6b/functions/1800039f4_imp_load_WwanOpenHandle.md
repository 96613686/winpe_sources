# __imp_load_WwanOpenHandle

- ea: `0x1800039f4`
- end: `0x180003a00`
- name: `__imp_load_WwanOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003963`

## import_xrefs

- `wwapi!WwanOpenHandle` at `0x1800039f4`

## pseudocode

```c
__int64 load_WwanOpenHandle()
{
  return _tailMerge_wwapi_dll();
}

```

## disassembly

```asm
0x1800039f4  lea     rax, __imp_WwanOpenHandle
0x1800039fb  jmp     __tailMerge_wwapi_dll
```
