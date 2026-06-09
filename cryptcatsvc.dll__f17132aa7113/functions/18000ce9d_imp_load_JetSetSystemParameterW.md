# __imp_load_JetSetSystemParameterW

- ea: `0x18000ce9d`
- end: `0x18000cea9`
- name: `__imp_load_JetSetSystemParameterW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetSetSystemParameterW` at `0x18000ce9d`

## pseudocode

```c
__int64 load_JetSetSystemParameterW()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000ce9d  lea     rax, __imp_JetSetSystemParameterW
0x18000cea4  jmp     __tailMerge_esent_dll
```
