# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RenderStatusControl::GetValueInternal

- ea: `0x24c30`
- end: `0x24dd8`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RenderStatusControl::GetValueInternal`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x24b90`

## callees

- `0x24c30`

## string_xrefs

- `0x24c72`: `service`

## pseudocode

```c

```

## disassembly

```asm
0x24c30  ldarg.1
0x24c31  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x24c36  brfalse.s loc_24C48
0x24c38  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24c3d  ldstr    aFormLabelStatu_0// "Form_Label_StatusNew"
0x24c42  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24c47  ret
0x24c48  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24c4d  ldstr    aFormLabelStatu_1// "Form_Label_StatusExisting"
0x24c52  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24c57  stloc.0
0x24c58  ldarg.1
0x24c59  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x24c5e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x24c63  stloc.1
0x24c64  ldloc.1
0x24c65  ldstr    aBusinessunit// "businessunit"
0x24c6a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24c6f  brtrue.s loc_24C90
0x24c71  ldloc.1
0x24c72  ldstr    aService// "service"
0x24c77  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24c7c  brtrue.s loc_24CC8
0x24c7e  ldloc.1
0x24c7f  ldstr    aAsyncoperation// "asyncoperation"
0x24c84  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24c89  brtrue.s loc_24D00
0x24c8b  br       loc_24D65
0x24c90  ldarg.1
0x24c91  ldstr    aIsdisabled// "isdisabled"
0x24c96  ldloc.0
0x24c97  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string, string)
0x24c9c  ldstr    a0// "0"
0x24ca1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24ca6  brtrue.s loc_24CB8
0x24ca8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24cad  ldstr    aFormLabelStatu_2// "Form_Label_StatusDisabled"
0x24cb2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24cb7  ret
0x24cb8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24cbd  ldstr    aFormLabelStatu_3// "Form_Label_StatusEnabled"
0x24cc2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24cc7  ret
0x24cc8  ldarg.1
0x24cc9  ldstr    aIsschedulable// "isschedulable"
0x24cce  ldloc.0
0x24ccf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string, string)
0x24cd4  ldstr    a0// "0"
0x24cd9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24cde  brtrue.s loc_24CF0
0x24ce0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24ce5  ldstr    aDialogLabelAct// "Dialog_Label_Active"
0x24cea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24cef  ret
0x24cf0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24cf5  ldstr    aDialogLabelIna// "Dialog_Label_Inactive"
0x24cfa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24cff  ret
0x24d00  ldarg.1
0x24d01  ldstr    aStatuscode// "statuscode"
0x24d06  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x24d0b  brfalse  loc_24DD6
0x24d10  ldarg.1
0x24d11  ldstr    aStatuscode// "statuscode"
0x24d16  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x24d1b  unbox.any [mscorlib]System.Int32
0x24d20  stloc.2
0x24d21  ldarg.1
0x24d22  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x24d27  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x24d2c  ldstr    aStatuscode// "statuscode"
0x24d31  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x24d36  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata
0x24d3b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStatusOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata::get_StatusOptions()
0x24d40  ldloc.2
0x24d41  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionsByValueCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption>::get_Item(!!T0)
0x24d46  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x24d4b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x24d50  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x24d55  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24d5a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24d5f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x24d64  ret
0x24d65  ldarg.1
0x24d66  ldstr    aStatecode// "statecode"
0x24d6b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x24d70  brfalse.s loc_24DD6
0x24d72  ldarg.1
0x24d73  ldstr    aStatecode// "statecode"
0x24d78  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x24d7d  isinst   [mscorlib]System.String
0x24d82  stloc.3
0x24d83  ldarg.1
0x24d84  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x24d89  ldloc.3
0x24d8a  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x24d8f  stloc.s  4
0x24d91  ldarg.1
0x24d92  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x24d97  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x24d9c  ldstr    aStatecode// "statecode"
0x24da1  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x24da6  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0x24dab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStateOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata::get_StateOptions()
0x24db0  ldloc.s  4
0x24db2  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionsByValueCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption>::get_Item(!!T0)
0x24db7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x24dbc  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x24dc1  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x24dc6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24dcb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24dd0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x24dd5  ret
0x24dd6  ldloc.0
0x24dd7  ret
```
