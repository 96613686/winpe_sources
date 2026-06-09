# Microsoft.Crm.Transformations.ResourceProvider::GetResourceManager

- ea: `0x2730`
- end: `0x273b`
- name: `Microsoft.Crm.Transformations.ResourceProvider::GetResourceManager`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2740`

## callees

- `0x2680`

## pseudocode

```c

```

## disassembly

```asm
0x2730  call     void Microsoft.Crm.Transformations.ResourceProvider::InitResourceManager()
0x2735  ldsfld   class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Transformations.ResourceProvider::_resourceManager
0x273a  ret
```
