# __imp_load_?DmCreateTask@@YAJPEBG0000K@Z

- ea: `0x1800047f2`
- end: `0x1800047fe`
- name: `__imp_load_?DmCreateTask@@YAJPEBG0000K@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800045f9`

## import_xrefs

- `DMCmnUtils!DmCreateTask` at `0x1800047f2`

## pseudocode

```c
__int64 load__DmCreateTask__YAJPEBG0000K_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x1800047f2  lea     rax, __imp_?DmCreateTask@@YAJPEBG0000K@Z; DmCreateTask(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x1800047f9  jmp     __tailMerge_dmcmnutils_dll
```
