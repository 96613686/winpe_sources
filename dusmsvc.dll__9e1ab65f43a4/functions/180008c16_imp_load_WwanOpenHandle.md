# __imp_load_WwanOpenHandle

- ea: `0x180008c16`
- end: `0x180008c22`
- name: `__imp_load_WwanOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008b85`

## import_xrefs

- `wwapi!WwanOpenHandle` at `0x180008c16`

## pseudocode

```c
__int64 load_WwanOpenHandle()
{
  return _tailMerge_wwapi_dll();
}

```

## disassembly

```asm
0x180008c16  lea     rax, __imp_WwanOpenHandle
0x180008c1d  jmp     __tailMerge_wwapi_dll
```
