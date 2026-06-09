# Microsoft.Crm.Application.WebServices.SystemCustomization.LookupImportHelper::GetLookupList

- ea: `0x7b10`
- end: `0x7d29`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.LookupImportHelper::GetLookupList`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x54d0`

## callees

- `0x7aa0`
- `0x7b10`

## pseudocode

```c

```

## disassembly

```asm
0x7b10  ldarg.s  4
0x7b12  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x7b17  stloc.0
0x7b18  ldarg.2
0x7b19  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesFrom()
0x7b1e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x7b23  stloc.1
0x7b24  br       loc_7D07
0x7b29  ldloc.1
0x7b2a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7b2f  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship
0x7b34  stloc.2
0x7b35  ldloc.2
0x7b36  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x7b3b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x7b40  ldarg.3
0x7b41  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7b46  brfalse  loc_7D07
0x7b4b  ldloc.0
0x7b4c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7b51  ldloc.2
0x7b52  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x7b57  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x7b5c  ldc.i4.1
0x7b5d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x7b62  stloc.3
0x7b63  ldarg.2
0x7b64  ldarg.3
0x7b65  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x7b6a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ReferencedEntityObjectTypeCode()
0x7b6f  stloc.s  4
0x7b71  ldloc.s  4
0x7b73  brfalse.s loc_7B82
0x7b75  ldloc.s  4
0x7b77  ldloc.3
0x7b78  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7b7d  bne.un   loc_7D07
0x7b82  ldnull
0x7b83  stloc.s  5
0x7b85  ldloc.3
0x7b86  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x7b8b  brfalse.s loc_7BA3
0x7b8d  ldloc.3
0x7b8e  ldloc.3
0x7b8f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x7b94  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x7b99  ldc.i4.1
0x7b9a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x7b9f  stloc.s  5
0x7ba1  br.s     loc_7BC5
0x7ba3  ldarg.s  4
0x7ba5  ldc.i4.s 0x18
0x7ba7  ldstr    aNoPrimaryField// "No primary field exist for entity {0} "
0x7bac  ldc.i4.1
0x7bad  newarr   [mscorlib]System.Object
0x7bb2  dup
0x7bb3  ldc.i4.0
0x7bb4  ldloc.2
0x7bb5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x7bba  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x7bbf  stelem.ref
0x7bc0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7bc5  ldloc.3
0x7bc6  ldloc.3
0x7bc7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x7bcc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x7bd1  ldc.i4.1
0x7bd2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x7bd7  stloc.s  6
0x7bd9  ldarg.s  6
0x7bdb  ldarg.0
0x7bdc  ldarg.1
0x7bdd  ldc.i4.1
0x7bde  stloc.s  7
0x7be0  ldloca.s 7
0x7be2  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.LookupTypeCode
0x7be8  callvirt instance string [mscorlib]System.Object::ToString()
0x7bed  ldloc.2
0x7bee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x7bf3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x7bf8  ldloc.3
0x7bf9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x7bfe  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x7c03  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Application.WebServices.SystemCustomization.LookupImportHelper::GetLookupMappingObject(valuetype [mscorlib]System.Guid columnMappingId, string lookupType, string lookupEntityName, string lookupAttributeName)
0x7c08  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::Add(var<u1>)
0x7c0d  ldarg.s  6
0x7c0f  ldarg.0
0x7c10  ldarg.1
0x7c11  ldc.i4.1
0x7c12  stloc.s  7
0x7c14  ldloca.s 7
0x7c16  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.LookupTypeCode
0x7c1c  callvirt instance string [mscorlib]System.Object::ToString()
0x7c21  ldloc.2
0x7c22  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x7c27  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x7c2c  ldloc.3
0x7c2d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x7c32  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x7c37  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Application.WebServices.SystemCustomization.LookupImportHelper::GetLookupMappingObject(valuetype [mscorlib]System.Guid columnMappingId, string lookupType, string lookupEntityName, string lookupAttributeName)
0x7c3c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::Add(var<u1>)
0x7c41  ldloc.3
0x7c42  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x7c47  ldarg.2
0x7c48  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x7c4d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7c52  brfalse  loc_7D07
0x7c57  ldloc.s  5
0x7c59  brfalse.s loc_7CB1
0x7c5b  ldloc.s  5
0x7c5d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x7c62  ldarg.s  5
0x7c64  ldloc.0
0x7c65  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7c6a  brfalse.s loc_7CB1
0x7c6c  ldarg.s  6
0x7c6e  ldarg.0
0x7c6f  ldarg.1
0x7c70  ldc.i4.0
0x7c71  stloc.s  7
0x7c73  ldloca.s 7
0x7c75  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.LookupTypeCode
0x7c7b  callvirt instance string [mscorlib]System.Object::ToString()
0x7c80  ldloc.3
0x7c81  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x7c86  ldarg.s  5
0x7c88  ldloc.0
0x7c89  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7c8e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x7c93  ldloc.s  5
0x7c95  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x7c9a  ldarg.s  5
0x7c9c  ldloc.0
0x7c9d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7ca2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x7ca7  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Application.WebServices.SystemCustomization.LookupImportHelper::GetLookupMappingObject(valuetype [mscorlib]System.Guid columnMappingId, string lookupType, string lookupEntityName, string lookupAttributeName)
0x7cac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::Add(var<u1>)
0x7cb1  ldloc.s  6
0x7cb3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x7cb8  ldarg.s  5
0x7cba  ldloc.0
0x7cbb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7cc0  brfalse.s loc_7D07
0x7cc2  ldarg.s  6
0x7cc4  ldarg.0
0x7cc5  ldarg.1
0x7cc6  ldc.i4.0
0x7cc7  stloc.s  7
0x7cc9  ldloca.s 7
0x7ccb  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.LookupTypeCode
0x7cd1  callvirt instance string [mscorlib]System.Object::ToString()
0x7cd6  ldloc.3
0x7cd7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x7cdc  ldarg.s  5
0x7cde  ldloc.0
0x7cdf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7ce4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x7ce9  ldloc.s  6
0x7ceb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x7cf0  ldarg.s  5
0x7cf2  ldloc.0
0x7cf3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7cf8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x7cfd  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Application.WebServices.SystemCustomization.LookupImportHelper::GetLookupMappingObject(valuetype [mscorlib]System.Guid columnMappingId, string lookupType, string lookupEntityName, string lookupAttributeName)
0x7d02  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::Add(var<u1>)
0x7d07  ldloc.1
0x7d08  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7d0d  brtrue   loc_7B29
0x7d12  leave.s  loc_7D28
0x7d14  ldloc.1
0x7d15  isinst   [mscorlib]System.IDisposable
0x7d1a  stloc.s  8
0x7d1c  ldloc.s  8
0x7d1e  brfalse.s loc_7D27
0x7d20  ldloc.s  8
0x7d22  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7d27  endfinally
0x7d28  ret
```
