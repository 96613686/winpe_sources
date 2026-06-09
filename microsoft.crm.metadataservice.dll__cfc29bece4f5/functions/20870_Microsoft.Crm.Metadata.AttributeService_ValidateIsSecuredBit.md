# Microsoft.Crm.Metadata.AttributeService::ValidateIsSecuredBit

- ea: `0x20870`
- end: `0x209f2`
- name: `Microsoft.Crm.Metadata.AttributeService::ValidateIsSecuredBit`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1ff00`

## callees

- `0x18490`
- `0x18630`
- `0x18760`
- `0x20870`
- `0x20a50`
- `0x23500`
- `0x76070`

## string_xrefs

- `0x208e0`: `canbesecuredforcreate`
- `0x2089e`: `canbesecuredforread`
- `0x208bf`: `canbesecuredforupdate`

## pseudocode

```c

```

## disassembly

```asm
0x20870  newobj   instance void <>c__DisplayClass104_0::.ctor()
0x20875  stloc.0
0x20876  ldloc.0
0x20877  ldarg.2
0x20878  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass104_0::context
0x2087d  ldarg.0
0x2087e  callvirt instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsSecured()
0x20883  brfalse  loc_209F1
0x20888  ldarg.1
0x20889  ldstr    aIssecured// "issecured"
0x2088e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x20893  unbox.any [mscorlib]System.Boolean
0x20898  brtrue   loc_209F1
0x2089d  ldarg.1
0x2089e  ldstr    aCanbesecuredfo_0// "canbesecuredforread"
0x208a3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x208a8  unbox.any [mscorlib]System.Boolean
0x208ad  brtrue.s loc_208BC
0x208af  ldarg.0
0x208b0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x208b5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_CanBeSecuredForRead()
0x208ba  br.s     loc_208BD
0x208bc  ldc.i4.1
0x208bd  stloc.1
0x208be  ldarg.1
0x208bf  ldstr    aCanbesecuredfo_1// "canbesecuredforupdate"
0x208c4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x208c9  unbox.any [mscorlib]System.Boolean
0x208ce  brtrue.s loc_208DD
0x208d0  ldarg.0
0x208d1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x208d6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_CanBeSecuredForUpdate()
0x208db  br.s     loc_208DE
0x208dd  ldc.i4.1
0x208de  stloc.2
0x208df  ldarg.1
0x208e0  ldstr    aCanbesecuredfo// "canbesecuredforcreate"
0x208e5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x208ea  unbox.any [mscorlib]System.Boolean
0x208ef  brtrue.s loc_208FE
0x208f1  ldarg.0
0x208f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x208f7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_CanBeSecuredForCreate()
0x208fc  br.s     loc_208FF
0x208fe  ldc.i4.1
0x208ff  ldloc.1
0x20900  or
0x20901  ldloc.2
0x20902  or
0x20903  brtrue.s loc_2091F
0x20905  ldc.i4   0x8004F501
0x2090a  ldc.i4.1
0x2090b  newarr   [mscorlib]System.Object
0x20910  dup
0x20911  ldc.i4.0
0x20912  ldarg.0
0x20913  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x20918  stelem.ref
0x20919  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2091e  throw
0x2091f  ldarg.0
0x20920  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x20925  ldloc.0
0x20926  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass104_0::context
0x2092b  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata> Microsoft.Crm.Metadata.AttributeService::GetParentEntityKeysIfAny(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription attribute, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x20930  stloc.3
0x20931  ldloc.3
0x20932  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata>::get_Count()
0x20937  brfalse  loc_209F1
0x2093c  ldloc.3
0x2093d  ldloc.0
0x2093e  ldftn    instance string <>c__DisplayClass104_0::<ValidateIsSecuredBit>b__0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata key)
0x20944  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata, string>::.ctor(object, native int)
0x20949  call     T0x2B000014
0x2094e  call     T0x2B000005
0x20953  stloc.s  4
0x20955  ldloc.s  4
0x20957  ldc.i4.0
0x20958  ldelem.ref
0x20959  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x2095e  stloc.s  5
0x20960  ldc.i4.1
0x20961  stloc.s  8
0x20963  br.s     loc_20982
0x20965  ldloc.s  5
0x20967  ldstr    asc_83CFE// ", "
0x2096c  ldloc.s  4
0x2096e  ldloc.s  8
0x20970  ldelem.ref
0x20971  call     string [mscorlib]System.String::Concat(string, string)
0x20976  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2097b  pop
0x2097c  ldloc.s  8
0x2097e  ldc.i4.1
0x2097f  add
0x20980  stloc.s  8
0x20982  ldloc.s  8
0x20984  ldloc.3
0x20985  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata>::get_Count()
0x2098a  blt.s    loc_20965
0x2098c  ldnull
0x2098d  stloc.s  6
0x2098f  ldnull
0x20990  stloc.s  7
0x20992  ldarg.1
0x20993  ldstr    aAttributeid// "attributeid"
0x20998  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2099d  unbox.any [mscorlib]System.Guid
0x209a2  ldloc.0
0x209a3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass104_0::context
0x209a8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x209ad  ldloca.s 6
0x209af  ldloca.s 7
0x209b1  call     void Microsoft.Crm.Metadata.AttributeService::GetExistingAttributeDisplayInformation(valuetype [mscorlib]System.Guid attributeId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection& displayNames, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection& descriptions)
0x209b6  ldc.i4   0x80060896
0x209bb  ldc.i4.2
0x209bc  newarr   [mscorlib]System.Object
0x209c1  dup
0x209c2  ldc.i4.0
0x209c3  ldloc.s  6
0x209c5  ldloc.0
0x209c6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass104_0::context
0x209cb  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x209d0  ldloc.0
0x209d1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass104_0::context
0x209d6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x209db  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x209e0  stelem.ref
0x209e1  dup
0x209e2  ldc.i4.1
0x209e3  ldloc.s  5
0x209e5  callvirt instance string [mscorlib]System.Object::ToString()
0x209ea  stelem.ref
0x209eb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x209f0  throw
0x209f1  ret
```
