# __imp_load_RpcStringBindingComposeW

- ea: `0x18000b3c0`
- end: `0x18000b3cc`
- name: `__imp_load_RpcStringBindingComposeW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000aba0`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x18000b3c0`

## pseudocode

```c
__int64 load_RpcStringBindingComposeW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18000b3c0  lea     rax, __imp_RpcStringBindingComposeW
0x18000b3c7  jmp     __tailMerge_rpcrt4_dll
```
