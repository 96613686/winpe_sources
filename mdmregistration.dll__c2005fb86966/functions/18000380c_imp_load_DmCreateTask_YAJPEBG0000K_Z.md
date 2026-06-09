# __imp_load_?DmCreateTask@@YAJPEBG0000K@Z

- ea: `0x18000380c`
- end: `0x180003818`
- name: `__imp_load_?DmCreateTask@@YAJPEBG0000K@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!DmCreateTask` at `0x18000380c`

## pseudocode

```c
__int64 load__DmCreateTask__YAJPEBG0000K_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x18000380c  lea     rax, __imp_?DmCreateTask@@YAJPEBG0000K@Z; DmCreateTask(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x180003813  jmp     __tailMerge_dmcmnutils_dll
```
