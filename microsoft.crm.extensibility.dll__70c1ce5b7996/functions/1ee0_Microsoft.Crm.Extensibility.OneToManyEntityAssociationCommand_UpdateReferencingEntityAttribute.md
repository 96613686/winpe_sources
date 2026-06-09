# Microsoft.Crm.Extensibility.OneToManyEntityAssociationCommand::UpdateReferencingEntityAttribute

- ea: `0x1ee0`
- end: `0x1f32`
- name: `Microsoft.Crm.Extensibility.OneToManyEntityAssociationCommand::UpdateReferencingEntityAttribute`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1970`

## callees

- `0x1ee0`
- `0x1f40`

## string_xrefs

- `0x1ee8`: `Cannot update logical attribute`

## pseudocode

```c

```

## disassembly

```asm
0x1ee0  ldarg.1
0x1ee1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsLogical()
0x1ee6  brfalse.s loc_1EF3
0x1ee8  ldstr    aCannotUpdateLo// "Cannot update logical attribute"
0x1eed  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1ef2  throw
0x1ef3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x1ef8  stloc.0
0x1ef9  ldloc.0
0x1efa  ldarg.3
0x1efb  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x1f00  ldloc.0
0x1f01  ldarg.2
0x1f02  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x1f07  ldarg.s  5
0x1f09  brfalse.s loc_1F1B
0x1f0b  ldloc.0
0x1f0c  ldarg.1
0x1f0d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1f12  ldarg.s  4
0x1f14  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1f19  br.s     loc_1F28
0x1f1b  ldloc.0
0x1f1c  ldarg.1
0x1f1d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1f22  ldnull
0x1f23  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1f28  ldarg.0
0x1f29  ldloc.0
0x1f2a  ldarg.s  6
0x1f2c  call     instance void Microsoft.Crm.Extensibility.OneToManyEntityAssociationCommand::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity referencingEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1f31  ret
```
