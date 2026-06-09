# __imp_load_UnInitThread

- ea: `0x180003dc4`
- end: `0x180003dd0`
- name: `__imp_load_UnInitThread`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!UnInitThread` at `0x180003dc4`

## pseudocode

```c
__int64 load_UnInitThread()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180003dc4  lea     rax, __imp_UnInitThread
0x180003dcb  jmp     __tailMerge_dui70_dll
```
