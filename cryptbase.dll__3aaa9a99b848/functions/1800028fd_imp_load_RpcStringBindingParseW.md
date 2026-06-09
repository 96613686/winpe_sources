# __imp_load_RpcStringBindingParseW

- ea: `0x1800028fd`
- end: `0x180002909`
- name: `__imp_load_RpcStringBindingParseW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002824`

## import_xrefs

- `RPCRT4!RpcStringBindingParseW` at `0x1800028fd`

## pseudocode

```c
__int64 __fastcall load_RpcStringBindingParseW(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_rpcrt4_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800028fd  lea     rax, __imp_RpcStringBindingParseW
0x180002904  jmp     __tailMerge_rpcrt4_dll
```
