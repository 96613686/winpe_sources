# __imp_load_ProcessPrng

- ea: `0x1800029be`
- end: `0x1800029ca`
- name: `__imp_load_ProcessPrng`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000293f`

## import_xrefs

- `bcryptPrimitives!ProcessPrng` at `0x1800029be`

## pseudocode

```c
__int64 __fastcall load_ProcessPrng(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_bcryptprimitives_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800029be  lea     rax, __imp_ProcessPrng
0x1800029c5  jmp     __tailMerge_bcryptprimitives_dll
```
