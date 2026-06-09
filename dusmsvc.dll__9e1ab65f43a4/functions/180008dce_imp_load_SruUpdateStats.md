# __imp_load_SruUpdateStats

- ea: `0x180008dce`
- end: `0x180008dda`
- name: `__imp_load_SruUpdateStats`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180008d4f`

## import_xrefs

- `SrumAPI!SruUpdateStats` at `0x180008dce`

## pseudocode

```c
__int64 load_SruUpdateStats()
{
  return _tailMerge_srumapi_dll();
}

```

## disassembly

```asm
0x180008dce  lea     rax, __imp_SruUpdateStats
0x180008dd5  jmp     __tailMerge_srumapi_dll
```
