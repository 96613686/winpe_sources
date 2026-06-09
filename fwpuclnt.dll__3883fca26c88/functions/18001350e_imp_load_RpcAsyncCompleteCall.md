# __imp_load_RpcAsyncCompleteCall

- ea: `0x18001350e`
- end: `0x18001351a`
- name: `__imp_load_RpcAsyncCompleteCall`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001347d`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18001350e`

## pseudocode

```c
__int64 load_RpcAsyncCompleteCall()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001350e  lea     rax, __imp_RpcAsyncCompleteCall
0x180013515  jmp     __tailMerge_rpcrt4_dll
```
