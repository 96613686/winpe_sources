# __imp_load_UnInitThread

- ea: `0x180002582`
- end: `0x18000258e`
- name: `__imp_load_UnInitThread`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800023b4`

## import_xrefs

- `DUI70!UnInitThread` at `0x180002582`

## pseudocode

```c
__int64 load_UnInitThread()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002582  lea     rax, __imp_UnInitThread
0x180002589  jmp     __tailMerge_dui70_dll
```
