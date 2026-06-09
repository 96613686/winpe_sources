# __imp_load_RpcStringBindingComposeW

- ea: `0x180015d3a`
- end: `0x180015d46`
- name: `__imp_load_RpcStringBindingComposeW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001592c`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180015d3a`

## pseudocode

```c
__int64 load_RpcStringBindingComposeW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180015d3a  lea     rax, __imp_RpcStringBindingComposeW
0x180015d41  jmp     __tailMerge_rpcrt4_dll
```
