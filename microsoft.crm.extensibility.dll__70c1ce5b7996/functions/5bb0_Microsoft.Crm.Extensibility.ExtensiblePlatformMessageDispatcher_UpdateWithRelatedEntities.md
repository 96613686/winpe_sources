# Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::UpdateWithRelatedEntities

- ea: `0x5bb0`
- end: `0x5bd1`
- name: `Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::UpdateWithRelatedEntities`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5930`

## callees

- `0x5be0`
- `0x5c40`

## string_xrefs

- `0x5bbf`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x5bb0  ldarg.0
0x5bb1  ldarg.1
0x5bb2  ldarg.0
0x5bb3  ldc.i4.2
0x5bb4  ldarg.1
0x5bb5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x5bba  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5bbf  ldstr    aUpdate// "Update"
0x5bc4  ldarg.2
0x5bc5  call     instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::GetDefaultEntityStateFromContext(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState defaultState, string entityName, string messageName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5bca  ldarg.2
0x5bcb  call     instance void Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::HandleRelatedEntities(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity primaryEntity, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState defaultState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5bd0  ret
```
