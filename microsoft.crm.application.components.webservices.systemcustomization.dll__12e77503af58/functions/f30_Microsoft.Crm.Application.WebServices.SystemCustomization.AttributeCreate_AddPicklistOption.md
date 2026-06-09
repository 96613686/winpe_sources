# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::AddPicklistOption

- ea: `0xf30`
- end: `0xff2`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::AddPicklistOption`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xbe0`

## callees

- `0xf30`

## string_xrefs

- `0xf53`: `Cannot create/update picklist. Option values must be unique`

## pseudocode

```c

```

## disassembly

```asm
0xf30  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf35  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xf3a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xf3f  stloc.0
0xf40  ldarg.0
0xf41  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0xf46  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0xf4b  ldarg.1
0xf4c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::ContainsKey(var<u1>)
0xf51  brfalse.s loc_F63
0xf53  ldstr    aCannotCreateUp// "Cannot create/update picklist. Option v"...
0xf58  ldc.i4   0x80040203
0xf5d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xf62  throw
0xf63  ldarg.s  6
0xf65  ldarg.s  4
0xf67  ldloc.0
0xf68  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf6d  stloc.1
0xf6e  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0xf73  stloc.2
0xf74  ldloc.2
0xf75  ldloc.1
0xf76  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0xf7b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0xf80  stloc.3
0xf81  ldarg.s  5
0xf83  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf88  brtrue.s loc_F9C
0xf8a  ldarg.s  6
0xf8c  ldarg.s  5
0xf8e  ldloc.0
0xf8f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf94  stloc.1
0xf95  ldloc.3
0xf96  ldloc.1
0xf97  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0xf9c  ldloc.0
0xf9d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfa2  dup
0xfa3  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0xfa8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_AttributePicklistValueId(valuetype [mscorlib]System.Guid)
0xfad  dup
0xfae  ldarg.1
0xfaf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_Value(int32)
0xfb4  dup
0xfb5  ldarg.s  7
0xfb7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_ExternalValue(string)
0xfbc  dup
0xfbd  ldarg.2
0xfbe  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_Color(string)
0xfc3  dup
0xfc4  ldarg.3
0xfc5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_ParentValues(class [mscorlib]System.Collections.Generic.IList`1<int32>)
0xfca  ldloc.2
0xfcb  ldloc.3
0xfcc  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PreloadedEnumOptionMetadataDataProviderFull::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0xfd1  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistOption::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributePicklistValueDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionMetadataDataProvider)
0xfd6  stloc.s  4
0xfd8  ldarg.0
0xfd9  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0xfde  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0xfe3  ldloc.s  4
0xfe5  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0xfea  ldloc.s  4
0xfec  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::Add(var<u1>, !!T0)
0xff1  ret
```
