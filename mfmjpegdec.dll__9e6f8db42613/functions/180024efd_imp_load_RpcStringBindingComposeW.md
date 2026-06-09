# __imp_load_RpcStringBindingComposeW

- ea: `0x180024efd`
- end: `0x180024f09`
- name: `__imp_load_RpcStringBindingComposeW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180024e5a`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180024efd`

## pseudocode

```c
__int64 load_RpcStringBindingComposeW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180024efd  lea     rax, __imp_RpcStringBindingComposeW
0x180024f04  jmp     __tailMerge_rpcrt4_dll
```
