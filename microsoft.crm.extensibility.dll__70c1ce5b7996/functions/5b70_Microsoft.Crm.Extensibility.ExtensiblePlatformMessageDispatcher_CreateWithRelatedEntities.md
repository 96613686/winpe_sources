# Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::CreateWithRelatedEntities

- ea: `0x5b70`
- end: `0x5bad`
- name: `Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::CreateWithRelatedEntities`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x56f0`

## callees

- `0x5be0`
- `0x5c40`

## string_xrefs

- `0x5b7f`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x5b70  ldarg.0
0x5b71  ldarg.1
0x5b72  ldarg.0
0x5b73  ldc.i4.1
0x5b74  ldarg.1
0x5b75  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x5b7a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5b7f  ldstr    aCreate// "Create"
0x5b84  ldarg.2
0x5b85  call     instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::GetDefaultEntityStateFromContext(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState defaultState, string entityName, string messageName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b8a  ldarg.2
0x5b8b  call     instance void Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::HandleRelatedEntities(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity primaryEntity, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState defaultState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b90  ldarg.1
0x5b91  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x5b96  unbox.any [mscorlib]System.Guid
0x5b9b  ldarg.1
0x5b9c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x5ba1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5ba6  ldarg.2
0x5ba7  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5bac  ret
```
