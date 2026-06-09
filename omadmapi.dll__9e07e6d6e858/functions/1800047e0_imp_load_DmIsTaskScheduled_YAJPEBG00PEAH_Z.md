# __imp_load_?DmIsTaskScheduled@@YAJPEBG00PEAH@Z

- ea: `0x1800047e0`
- end: `0x1800047ec`
- name: `__imp_load_?DmIsTaskScheduled@@YAJPEBG00PEAH@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800045f9`

## import_xrefs

- `DMCmnUtils!DmIsTaskScheduled` at `0x1800047e0`

## pseudocode

```c
__int64 load__DmIsTaskScheduled__YAJPEBG00PEAH_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x1800047e0  lea     rax, __imp_?DmIsTaskScheduled@@YAJPEBG00PEAH@Z; DmIsTaskScheduled(ushort const *,ushort const *,ushort const *,int *)
0x1800047e7  jmp     __tailMerge_dmcmnutils_dll
```
