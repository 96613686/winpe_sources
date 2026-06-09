# Microsoft.Crm.Platform.Server.InjectProcessInstanceAttributesExtension::BlankoutProcessRelatedFields

- ea: `0x4e0f0`
- end: `0x4e115`
- name: `Microsoft.Crm.Platform.Server.InjectProcessInstanceAttributesExtension::BlankoutProcessRelatedFields`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x4e090`

## string_xrefs

- `0x4e0f1`: `processid`
- `0x4e109`: `traversedpath`

## pseudocode

```c

```

## disassembly

```asm
0x4e0f0  ldarg.1
0x4e0f1  ldstr    aProcessid// "processid"
0x4e0f6  ldnull
0x4e0f7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x4e0fc  ldarg.1
0x4e0fd  ldstr    aStageid// "stageid"
0x4e102  ldnull
0x4e103  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x4e108  ldarg.1
0x4e109  ldstr    aTraversedpath// "traversedpath"
0x4e10e  ldnull
0x4e10f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x4e114  ret
```
