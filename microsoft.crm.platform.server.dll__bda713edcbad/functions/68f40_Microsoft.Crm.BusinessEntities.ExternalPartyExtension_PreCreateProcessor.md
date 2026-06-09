# Microsoft.Crm.BusinessEntities.ExternalPartyExtension::PreCreateProcessor

- ea: `0x68f40`
- end: `0x6903a`
- name: `Microsoft.Crm.BusinessEntities.ExternalPartyExtension::PreCreateProcessor`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x66b10`
- `0x66b60`
- `0x688c0`
- `0x68910`
- `0x68f40`
- `0x69040`
- `0x691b0`

## string_xrefs

- `0x68fbf`: `createdonbehalfby`
- `0x68f5d`: `RegardingObject '{0}' of type '{1}' don't have create access for entity '{2}'`
- `0x68fff`: `createdbyexternalparty`

## pseudocode

```c

```

## disassembly

```asm
0x68f40  ldarg.3
0x68f41  switch   loc_68F58, loc_68FA7, loc_68FB1
0x68f52  ldarg.3
0x68f53  ldc.i4.8
0x68f54  beq.s    loc_68FB9
0x68f56  br.s     loc_68FB9
0x68f58  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x68f5d  ldstr    aRegardingobjec_3// "RegardingObject '{0}' of type '{1}' don"...
0x68f62  ldc.i4.3
0x68f63  newarr   [mscorlib]System.Object
0x68f68  dup
0x68f69  ldc.i4.0
0x68f6a  ldarg.2
0x68f6b  ldfld    valuetype [mscorlib]System.Guid LocalContextData::RegardingObjectId
0x68f70  box      [mscorlib]System.Guid
0x68f75  stelem.ref
0x68f76  dup
0x68f77  ldc.i4.1
0x68f78  ldarg.2
0x68f79  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata LocalContextData::RegardingObjectMetadata
0x68f7e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x68f83  stelem.ref
0x68f84  dup
0x68f85  ldc.i4.2
0x68f86  ldarg.1
0x68f87  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x68f8c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x68f91  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x68f96  stelem.ref
0x68f97  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x68f9c  ldc.i4   0x8006110A
0x68fa1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x68fa6  throw
0x68fa7  ldarg.0
0x68fa8  ldarg.1
0x68fa9  ldarg.2
0x68faa  call     instance void Microsoft.Crm.BusinessEntities.ExternalPartyExtension::ValidateCreateForEntityReference(class Microsoft.Crm.BusinessEntities.ExtensionEventArgs e, valuetype LocalContextData localContext)
0x68faf  br.s     loc_68FB9
0x68fb1  ldarg.0
0x68fb2  ldarg.1
0x68fb3  ldarg.2
0x68fb4  call     instance void Microsoft.Crm.BusinessEntities.ExternalPartyExtension::ValidateCreateForParentEntityReference(class Microsoft.Crm.BusinessEntities.ExtensionEventArgs e, valuetype LocalContextData localContext)
0x68fb9  ldarg.1
0x68fba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x68fbf  ldstr    aCreatedonbehal// "createdonbehalfby"
0x68fc4  ldarg.1
0x68fc5  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x68fca  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x68fcf  box      [mscorlib]System.Guid
0x68fd4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x68fd9  ldarg.1
0x68fda  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x68fdf  ldstr    aModifiedonbeha// "modifiedonbehalfby"
0x68fe4  ldarg.1
0x68fe5  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x68fea  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x68fef  box      [mscorlib]System.Guid
0x68ff4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x68ff9  ldarg.1
0x68ffa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x68fff  ldstr    aCreatedbyexter// "createdbyexternalparty"
0x69004  ldarg.1
0x69005  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x6900a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_ExternalPartyId()
0x6900f  box      [mscorlib]System.Guid
0x69014  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x69019  ldarg.1
0x6901a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x6901f  ldstr    aModifiedbyexte// "modifiedbyexternalparty"
0x69024  ldarg.1
0x69025  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x6902a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_ExternalPartyId()
0x6902f  box      [mscorlib]System.Guid
0x69034  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x69039  ret
```
