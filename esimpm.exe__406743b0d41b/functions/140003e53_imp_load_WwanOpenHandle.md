# __imp_load_WwanOpenHandle

- ea: `0x140003e53`
- end: `0x140003e5f`
- name: `__imp_load_WwanOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003db0`

## import_xrefs

- `wwapi!WwanOpenHandle` at `0x140003e53`

## pseudocode

```c
__int64 load_WwanOpenHandle()
{
  return _tailMerge_wwapi_dll();
}

```

## disassembly

```asm
0x140003e53  lea     rax, __imp_WwanOpenHandle
0x140003e5a  jmp     __tailMerge_wwapi_dll
```
