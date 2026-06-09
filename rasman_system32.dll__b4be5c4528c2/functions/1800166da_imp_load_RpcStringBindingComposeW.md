# __imp_load_RpcStringBindingComposeW

- ea: `0x1800166da`
- end: `0x1800166e6`
- name: `__imp_load_RpcStringBindingComposeW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800162cc`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x1800166da`

## pseudocode

```c
__int64 load_RpcStringBindingComposeW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x1800166da  lea     rax, __imp_RpcStringBindingComposeW
0x1800166e1  jmp     __tailMerge_rpcrt4_dll
```
