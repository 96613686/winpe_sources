# __imp_load_NDRCContextBinding

- ea: `0x180002933`
- end: `0x18000293f`
- name: `__imp_load_NDRCContextBinding`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002824`

## import_xrefs

- `RPCRT4!NDRCContextBinding` at `0x180002933`

## pseudocode

```c
__int64 __fastcall load_NDRCContextBinding(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_rpcrt4_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002933  lea     rax, __imp_NDRCContextBinding
0x18000293a  jmp     __tailMerge_rpcrt4_dll
```
