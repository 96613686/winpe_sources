# __imp_load_DevObjOpenDevRegKey

- ea: `0x180006500`
- end: `0x18000650c`
- name: `__imp_load_DevObjOpenDevRegKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006427`

## import_xrefs

- `DEVOBJ!DevObjOpenDevRegKey` at `0x180006500`

## pseudocode

```c
__int64 load_DevObjOpenDevRegKey()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x180006500  lea     rax, __imp_DevObjOpenDevRegKey
0x180006507  jmp     __tailMerge_devobj_dll
```
