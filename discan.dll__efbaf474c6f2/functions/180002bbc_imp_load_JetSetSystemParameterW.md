# __imp_load_JetSetSystemParameterW

- ea: `0x180002bbc`
- end: `0x180002bc8`
- name: `__imp_load_JetSetSystemParameterW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetSetSystemParameterW` at `0x180002bbc`

## pseudocode

```c
__int64 load_JetSetSystemParameterW()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002bbc  lea     rax, __imp_JetSetSystemParameterW
0x180002bc3  jmp     __tailMerge_esent_dll
```
