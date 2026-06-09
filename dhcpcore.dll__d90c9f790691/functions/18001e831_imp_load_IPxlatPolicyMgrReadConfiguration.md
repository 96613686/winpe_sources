# __imp_load_IPxlatPolicyMgrReadConfiguration

- ea: `0x18001e831`
- end: `0x18001e83d`
- name: `__imp_load_IPxlatPolicyMgrReadConfiguration`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18001e7a0`

## import_xrefs

- `IPXLATCFG!IPxlatPolicyMgrReadConfiguration` at `0x18001e831`

## pseudocode

```c
__int64 load_IPxlatPolicyMgrReadConfiguration()
{
  return _tailMerge_ipxlatcfg_dll();
}

```

## disassembly

```asm
0x18001e831  lea     rax, __imp_IPxlatPolicyMgrReadConfiguration
0x18001e838  jmp     __tailMerge_ipxlatcfg_dll
```
