# ProvisioningCommandsMap::GetNodeMap(void)

- ea: `0x1800065b0`
- end: `0x1800065b8`
- name: `?GetNodeMap@ProvisioningCommandsMap@@UEBAPEBUCSP_NODEMAP_ENTRY@@XZ`
- size: `8`
- prototype: `const struct CSP_NODEMAP_ENTRY *__fastcall(ProvisioningCommandsMap *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
wchar_t **__fastcall ProvisioningCommandsMap::GetNodeMap(ProvisioningCommandsMap *this)
{
  return &`ProvisioningCommandsMap::GetNodeMap'::`2'::pNodeMap;
}

```

## disassembly

```asm
0x1800065b0  lea     rax, ?pNodeMap@?1??GetNodeMap@ProvisioningCommandsMap@@UEBAPEBUCSP_NODEMAP_ENTRY@@XZ@4PAU3@A; CSP_NODEMAP_ENTRY near * `ProvisioningCommandsMap::GetNodeMap(void)'::`2'::pNodeMap
0x1800065b7  retn
```
