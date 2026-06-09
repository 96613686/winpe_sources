# __imp_load_RpcStringFreeW

- ea: `0x1800028eb`
- end: `0x1800028f7`
- name: `__imp_load_RpcStringFreeW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002824`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1800028eb`

## pseudocode

```c
__int64 __fastcall load_RpcStringFreeW(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_rpcrt4_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800028eb  lea     rax, __imp_RpcStringFreeW
0x1800028f2  jmp     __tailMerge_rpcrt4_dll
```
