# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::RetrieveRelationShipName

- ea: `0x7cd0`
- end: `0x7e24`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::RetrieveRelationShipName`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x7420`

## callees

- `0x1350`
- `0x7cd0`

## string_xrefs

- `0x7d2d`: `Not able to retrieve EntityTypeName from FormDescriptor`

## pseudocode

```c

```

## disassembly

```asm
0x7cd0  ldarg.0
0x7cd1  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::PhoneCallRelationshipName
0x7cd6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7cdb  brfalse  loc_7E23
0x7ce0  ldarg.0
0x7ce1  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::TaskRelationshipName
0x7ce6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7ceb  brfalse  loc_7E23
0x7cf0  ldarg.0
0x7cf1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0x7cf6  brfalse  loc_7E23
0x7cfb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7d00  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7d05  stloc.0
0x7d06  ldarg.0
0x7d07  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0x7d0c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_EntityMetadata()
0x7d11  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x7d16  stloc.1
0x7d17  ldnull
0x7d18  stloc.2
0x7d19  ldloc.1
0x7d1a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x7d1f  brtrue.s loc_7D2C
0x7d21  ldloc.0
0x7d22  ldloc.1
0x7d23  ldc.i4.1
0x7d24  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x7d29  stloc.2
0x7d2a  br.s     loc_7D3E
0x7d2c  ldnull
0x7d2d  ldstr    aNotAbleToRetri_0// "Not able to retrieve EntityTypeName fro"...
0x7d32  ldc.i4.0
0x7d33  newarr   [mscorlib]System.Object
0x7d38  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x7d3d  ret
0x7d3e  ldc.i4.0
0x7d3f  stloc.3
0x7d40  ldloc.2
0x7d41  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesToEntityRelationships()
0x7d46  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipCollection
0x7d4b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::GetEnumerator()
0x7d50  stloc.s  4
0x7d52  br       loc_7E09
0x7d57  ldloc.s  4
0x7d59  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Current()
0x7d5e  stloc.s  5
0x7d60  ldloc.s  5
0x7d62  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_Relationships()
0x7d67  ldc.i4.0
0x7d68  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataArrayList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship>::get_Item(!!T0)
0x7d6d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x7d72  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7d77  ldloc.2
0x7d78  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7d7d  bne.un   loc_7E03
0x7d82  ldloc.s  5
0x7d84  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_Relationships()
0x7d89  ldc.i4.0
0x7d8a  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataArrayList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship>::get_Item(!!T0)
0x7d8f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x7d94  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x7d99  ldstr    aRegarding// "regarding"
0x7d9e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7da3  brfalse.s loc_7E03
0x7da5  ldloc.s  5
0x7da7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_Relationships()
0x7dac  ldc.i4.0
0x7dad  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataArrayList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship>::get_Item(!!T0)
0x7db2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0x7db7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7dbc  ldc.i4   0x1072
0x7dc1  bne.un.s loc_7DD4
0x7dc3  ldarg.0
0x7dc4  ldloc.s  5
0x7dc6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_SchemaName()
0x7dcb  stfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::PhoneCallRelationshipName
0x7dd0  ldloc.3
0x7dd1  ldc.i4.1
0x7dd2  add
0x7dd3  stloc.3
0x7dd4  ldloc.s  5
0x7dd6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_Relationships()
0x7ddb  ldc.i4.0
0x7ddc  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataArrayList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship>::get_Item(!!T0)
0x7de1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0x7de6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7deb  ldc.i4   0x1074
0x7df0  bne.un.s loc_7E03
0x7df2  ldarg.0
0x7df3  ldloc.s  5
0x7df5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_SchemaName()
0x7dfa  stfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::TaskRelationshipName
0x7dff  ldloc.3
0x7e00  ldc.i4.1
0x7e01  add
0x7e02  stloc.3
0x7e03  ldloc.3
0x7e04  ldc.i4.2
0x7e05  blt.s    loc_7E09
0x7e07  leave.s  loc_7E23
0x7e09  ldloc.s  4
0x7e0b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7e10  brtrue   loc_7D57
0x7e15  leave.s  loc_7E23
0x7e17  ldloc.s  4
0x7e19  brfalse.s loc_7E22
0x7e1b  ldloc.s  4
0x7e1d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7e22  endfinally
0x7e23  ret
```
