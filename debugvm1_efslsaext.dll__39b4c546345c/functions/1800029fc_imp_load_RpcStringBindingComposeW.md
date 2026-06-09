# __imp_load_RpcStringBindingComposeW

- ea: `0x1800029fc`
- end: `0x180002a08`
- name: `__imp_load_RpcStringBindingComposeW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000245c`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x1800029fc`

## pseudocode

```c
__int64 load_RpcStringBindingComposeW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x1800029fc  lea     rax, __imp_RpcStringBindingComposeW
0x180002a03  jmp     __tailMerge_rpcrt4_dll
```
