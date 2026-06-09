# Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::System.Data.Services.IUpdatable.RemoveReferenceFromCollection

- ea: `0x8160`
- end: `0x8233`
- name: `Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::System.Data.Services.IUpdatable.RemoveReferenceFromCollection`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x7040`
- `0x8160`
- `0x8410`
- `0x8a00`

## string_xrefs

- `0x8218`: `Property {0} does not represent a collection that resources can be removed from.`

## pseudocode

```c

```

## disassembly

```asm
0x8160  ldarg.1
0x8161  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::ValidateEntityResource(object resource)
0x8166  stloc.0
0x8167  ldarg.3
0x8168  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::ValidateEntityResource(object resource)
0x816d  stloc.1
0x816e  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OrganizationDataService::GetOrganizationContext()
0x8173  stloc.2
0x8174  ldloc.2
0x8175  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x817a  ldloc.0
0x817b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x8180  ldc.i4.1
0x8181  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x8186  stloc.3
0x8187  ldarg.0
0x8188  ldloc.3
0x8189  callvirt instance class [System.Data.Services]System.Data.Services.Providers.ResourceType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ResourceType()
0x818e  ldarg.2
0x818f  call     instance class [mscorlib]System.Tuple`3<class [System.Data.Services]System.Data.Services.Providers.ResourceAssociationSet, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole> Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::GetAssocationInformation(class [System.Data.Services]System.Data.Services.Providers.ResourceType type, string propertyName)
0x8194  stloc.s  4
0x8196  ldloc.s  4
0x8198  brfalse.s loc_8206
0x819a  ldloc.3
0x819b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x81a0  brfalse.s loc_81D0
0x81a2  ldloc.2
0x81a3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x81a8  ldloc.1
0x81a9  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x81ae  ldc.i4.1
0x81af  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x81b4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x81b9  ldstr    aActivityparty// "activityparty"
0x81be  call     bool [mscorlib]System.String::op_Equality(string, string)
0x81c3  brfalse.s loc_81D0
0x81c5  ldstr    aAnActivitypart// "An activityparty cannot be disassociate"...
0x81ca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x81cf  throw
0x81d0  ldloc.s  4
0x81d2  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [System.Data.Services]System.Data.Services.Providers.ResourceAssociationSet, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>::get_Item2()
0x81d7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_SchemaName()
0x81dc  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship::.ctor(string)
0x81e1  stloc.s  5
0x81e3  ldloc.s  5
0x81e5  ldloc.s  4
0x81e7  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [System.Data.Services]System.Data.Services.Providers.ResourceAssociationSet, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>::get_Item3()
0x81ec  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>::.ctor(var<u1>)
0x81f1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship::set_PrimaryEntityRole(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>)
0x81f6  ldarg.0
0x81f7  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceContext Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::_context
0x81fc  ldloc.0
0x81fd  ldloc.s  5
0x81ff  ldloc.1
0x8200  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteLink(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x8205  ret
0x8206  ldc.i4   0x80040216
0x820b  ldc.i4.1
0x820c  newarr   [mscorlib]System.Object
0x8211  dup
0x8212  ldc.i4.0
0x8213  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8218  ldstr    aProperty0DoesN_0// "Property {0} does not represent a colle"...
0x821d  ldc.i4.1
0x821e  newarr   [mscorlib]System.Object
0x8223  dup
0x8224  ldc.i4.0
0x8225  ldarg.2
0x8226  stelem.ref
0x8227  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x822c  stelem.ref
0x822d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x8232  throw
```
