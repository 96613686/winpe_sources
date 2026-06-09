# Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::RetrieveFieldPermissionsFromCurrentProfile

- ea: `0xbfa00`
- end: `0xbfbb7`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::RetrieveFieldPermissionsFromCurrentProfile`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0xbf950`

## callees

- `0xbf590`
- `0xbf5b0`
- `0xbf5d0`
- `0xbf5f0`
- `0xbf610`
- `0xbf630`
- `0xbf650`
- `0xbf670`
- `0xbf690`
- `0xbfa00`
- `0xbfd30`
- `0xbfde0`
- `0xbfe10`

## string_xrefs

- `0xbfa14`: `fieldsecurityprofileid`
- `0xbfb29`: `canread`
- `0xbfb10`: `canupdate`
- `0xbfaf7`: `cancreate`

## pseudocode

```c

```

## disassembly

```asm
0xbfa00  ldarg.1
0xbfa01  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0xbfa06  stloc.0
0xbfa07  br       loc_BFB9F
0xbfa0c  ldloc.0
0xbfa0d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0xbfa12  stloc.1
0xbfa13  ldloc.1
0xbfa14  ldstr    aFieldsecurityp_1// "fieldsecurityprofileid"
0xbfa19  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbfa1e  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xbfa23  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xbfa28  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xbfa2d  ldarg.2
0xbfa2e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xbfa33  brfalse  loc_BFB9F
0xbfa38  ldarg.s  4
0xbfa3a  ldloc.1
0xbfa3b  ldstr    aEntityname// "entityname"
0xbfa40  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbfa45  castclass [mscorlib]System.String
0xbfa4a  ldc.i4.1
0xbfa4b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xbfa50  stloc.2
0xbfa51  ldloc.2
0xbfa52  ldloc.1
0xbfa53  ldstr    aAttributelogic// "attributelogicalname"
0xbfa58  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbfa5d  castclass [mscorlib]System.String
0xbfa62  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0xbfa67  stloc.3
0xbfa68  ldarg.0
0xbfa69  ldloc.3
0xbfa6a  call     instance bool Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::CanBeDisplayed(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0xbfa6f  brfalse  loc_BFB9F
0xbfa74  ldloc.2
0xbfa75  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xbfa7a  ldstr    asc_12F88A// "-"
0xbfa7f  ldloc.3
0xbfa80  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xbfa85  call     string [mscorlib]System.String::Concat(string, string, string)
0xbfa8a  stloc.s  4
0xbfa8c  ldarg.3
0xbfa8d  ldloc.s  4
0xbfa8f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::ContainsKey(var<u1>)
0xbfa94  brtrue   loc_BFB9F
0xbfa99  ldloca.s 5
0xbfa9b  initobj  Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION
0xbfaa1  ldloca.s 5
0xbfaa3  ldloc.1
0xbfaa4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xbfaa9  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xbfaae  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::set_fpId(valuetype [mscorlib]System.Guid value)
0xbfab3  ldloca.s 5
0xbfab5  ldloc.2
0xbfab6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xbfabb  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::set_EntityName(string value)
0xbfac0  ldloca.s 5
0xbfac2  ldarg.0
0xbfac3  ldloc.2
0xbfac4  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::GetDisplayName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMD)
0xbfac9  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::set_EntityDisplayName(string value)
0xbface  ldloca.s 5
0xbfad0  ldloc.3
0xbfad1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xbfad6  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::set_AttributeName(string value)
0xbfadb  ldloca.s 5
0xbfadd  ldarg.0
0xbfade  ldloc.3
0xbfadf  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::GetDisplayName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0xbfae4  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::set_AttributeDisplayName(string value)
0xbfae9  ldloca.s 5
0xbfaeb  ldloc.3
0xbfaec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xbfaf1  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::set_AttributeType(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo value)
0xbfaf6  ldloc.1
0xbfaf7  ldstr    aCancreate// "cancreate"
0xbfafc  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbfb01  unbox.any [mscorlib]System.Int32
0xbfb06  ldc.i4.4
0xbfb07  beq.s    loc_BFB0C
0xbfb09  ldc.i4.0
0xbfb0a  br.s     loc_BFB0D
0xbfb0c  ldc.i4.1
0xbfb0d  stloc.s  6
0xbfb0f  ldloc.1
0xbfb10  ldstr    aCanupdate// "canupdate"
0xbfb15  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbfb1a  unbox.any [mscorlib]System.Int32
0xbfb1f  ldc.i4.4
0xbfb20  beq.s    loc_BFB25
0xbfb22  ldc.i4.0
0xbfb23  br.s     loc_BFB26
0xbfb25  ldc.i4.1
0xbfb26  stloc.s  7
0xbfb28  ldloc.1
0xbfb29  ldstr    aCanread// "canread"
0xbfb2e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbfb33  unbox.any [mscorlib]System.Int32
0xbfb38  ldc.i4.4
0xbfb39  beq.s    loc_BFB3E
0xbfb3b  ldc.i4.0
0xbfb3c  br.s     loc_BFB3F
0xbfb3e  ldc.i4.1
0xbfb3f  stloc.s  8
0xbfb41  ldloca.s 5
0xbfb43  ldloc.3
0xbfb44  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForCreate()
0xbfb49  brfalse.s loc_BFB53
0xbfb4b  ldloc.3
0xbfb4c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanBeSecuredForCreate()
0xbfb51  brtrue.s loc_BFB56
0xbfb53  ldc.i4.2
0xbfb54  br.s     loc_BFB58
0xbfb56  ldloc.s  6
0xbfb58  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::set_Create(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess value)
0xbfb5d  ldloca.s 5
0xbfb5f  ldloc.3
0xbfb60  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForUpdate()
0xbfb65  brfalse.s loc_BFB6F
0xbfb67  ldloc.3
0xbfb68  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanBeSecuredForUpdate()
0xbfb6d  brtrue.s loc_BFB72
0xbfb6f  ldc.i4.2
0xbfb70  br.s     loc_BFB74
0xbfb72  ldloc.s  7
0xbfb74  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::set_Update(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess value)
0xbfb79  ldloca.s 5
0xbfb7b  ldloc.3
0xbfb7c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForRead()
0xbfb81  brfalse.s loc_BFB8B
0xbfb83  ldloc.3
0xbfb84  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanBeSecuredForRead()
0xbfb89  brtrue.s loc_BFB8E
0xbfb8b  ldc.i4.2
0xbfb8c  br.s     loc_BFB90
0xbfb8e  ldloc.s  8
0xbfb90  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::set_Read(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess value)
0xbfb95  ldarg.3
0xbfb96  ldloc.s  4
0xbfb98  ldloc.s  5
0xbfb9a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::Add(var<u1>, !!T0)
0xbfb9f  ldloc.0
0xbfba0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbfba5  brtrue   loc_BFA0C
0xbfbaa  leave.s  loc_BFBB6
0xbfbac  ldloc.0
0xbfbad  brfalse.s loc_BFBB5
0xbfbaf  ldloc.0
0xbfbb0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbfbb5  endfinally
0xbfbb6  ret
```
