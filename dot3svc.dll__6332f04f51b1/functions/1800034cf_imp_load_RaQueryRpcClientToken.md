# __imp_load_RaQueryRpcClientToken

- ea: `0x1800034cf`
- end: `0x1800034db`
- name: `__imp_load_RaQueryRpcClientToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800033c0`

## import_xrefs

- `MobileNetworking!RaQueryRpcClientToken` at `0x1800034cf`

## pseudocode

```c
__int64 load_RaQueryRpcClientToken()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x1800034cf  lea     rax, __imp_RaQueryRpcClientToken
0x1800034d6  jmp     __tailMerge_mobilenetworking_dll
```
