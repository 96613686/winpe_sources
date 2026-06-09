# Microsoft.Crm.BusinessEntities.ExternalPartyExtension::ValidateCreateForEntityReference

- ea: `0x691b0`
- end: `0x692ab`
- name: `Microsoft.Crm.BusinessEntities.ExternalPartyExtension::ValidateCreateForEntityReference`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x68f40`

## callees

- `0x688c0`
- `0x691b0`

## string_xrefs

- `0x69260`: `Invalid Owner Attribute Value to create new record. RegardingObject '{0}' of type '{1}' can't create entity '{2}'`
- `0x691d7`: `RegardingObject '{0}' of type '{1}' can't create entity '{2}'`

## pseudocode

```c

```

## disassembly

```asm
0x691b0  ldarg.1
0x691b1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x691b6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x691bb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x691c0  ldarg.2
0x691c1  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata LocalContextData::RegardingObjectMetadata
0x691c6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x691cb  callvirt instance bool [mscorlib]System.String::Equals(string)
0x691d0  brfalse.s loc_69221
0x691d2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x691d7  ldstr    aRegardingobjec_4// "RegardingObject '{0}' of type '{1}' can"...
0x691dc  ldc.i4.3
0x691dd  newarr   [mscorlib]System.Object
0x691e2  dup
0x691e3  ldc.i4.0
0x691e4  ldarg.2
0x691e5  ldfld    valuetype [mscorlib]System.Guid LocalContextData::RegardingObjectId
0x691ea  box      [mscorlib]System.Guid
0x691ef  stelem.ref
0x691f0  dup
0x691f1  ldc.i4.1
0x691f2  ldarg.2
0x691f3  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata LocalContextData::RegardingObjectMetadata
0x691f8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x691fd  stelem.ref
0x691fe  dup
0x691ff  ldc.i4.2
0x69200  ldarg.1
0x69201  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x69206  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x6920b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x69210  stelem.ref
0x69211  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x69216  ldc.i4   0x8006110A
0x6921b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x69220  throw
0x69221  ldarg.2
0x69222  ldfld    string LocalContextData::EntityReferenceAttribute
0x69227  stloc.0
0x69228  ldloc.0
0x69229  brfalse.s loc_6923E
0x6922b  ldarg.1
0x6922c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x69231  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x69236  ldloc.0
0x69237  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x6923c  br.s     loc_6923F
0x6923e  ldnull
0x6923f  stloc.1
0x69240  ldloc.1
0x69241  brfalse.s loc_6925B
0x69243  ldloc.1
0x69244  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x69249  unbox.any [mscorlib]System.Guid
0x6924e  ldarg.2
0x6924f  ldfld    valuetype [mscorlib]System.Guid LocalContextData::RegardingObjectId
0x69254  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x69259  brfalse.s loc_692AA
0x6925b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x69260  ldstr    aInvalidOwnerAt// "Invalid Owner Attribute Value to create"...
0x69265  ldc.i4.3
0x69266  newarr   [mscorlib]System.Object
0x6926b  dup
0x6926c  ldc.i4.0
0x6926d  ldarg.2
0x6926e  ldfld    valuetype [mscorlib]System.Guid LocalContextData::RegardingObjectId
0x69273  box      [mscorlib]System.Guid
0x69278  stelem.ref
0x69279  dup
0x6927a  ldc.i4.1
0x6927b  ldarg.2
0x6927c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata LocalContextData::RegardingObjectMetadata
0x69281  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x69286  stelem.ref
0x69287  dup
0x69288  ldc.i4.2
0x69289  ldarg.1
0x6928a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x6928f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x69294  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x69299  stelem.ref
0x6929a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6929f  ldc.i4   0x8006110A
0x692a4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x692a9  throw
0x692aa  ret
```
