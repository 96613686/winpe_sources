# __imp_load_InitThread

- ea: `0x18005850e`
- end: `0x18005851a`
- name: `__imp_load_InitThread`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800583ff`

## import_xrefs

- `DUI70!InitThread` at `0x18005850e`

## pseudocode

```c
__int64 load_InitThread()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18005850e  lea     rax, __imp_InitThread
0x180058515  jmp     __tailMerge_dui70_dll
```
