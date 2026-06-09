# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetStringInfo

- ea: `0xaf0`
- end: `0xbd4`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetStringInfo`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x190`
- `0x220`
- `0x240`
- `0x330`
- `0xaf0`
- `0x1b90`

## pseudocode

```c

```

## disassembly

```asm
0xaf0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaf5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xafa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xaff  stloc.0
0xb00  ldarg.1
0xb01  brtrue.s loc_B24
0xb03  ldarg.0
0xb04  ldstr    aLength// "length"
0xb09  ldc.i4.s 0x64
0xb0b  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0xb10  ldarg.0
0xb11  ldstr    aFormat// "format"
0xb16  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xb1b  ldloc.0
0xb1c  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.StringAttributeInfo::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb21  stloc.1
0xb22  br.s     loc_B55
0xb24  ldarg.1
0xb25  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeMetadata
0xb2a  stloc.2
0xb2b  ldarg.0
0xb2c  ldstr    aLength// "length"
0xb31  ldloc.2
0xb32  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata::get_MaxLength()
0xb37  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0xb3c  ldloc.2
0xb3d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0xb42  ldloc.0
0xb43  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.StringAttributeInfo::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb48  stloc.1
0xb49  ldloc.1
0xb4a  ldarg.1
0xb4b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_YomiOf()
0xb50  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.StringAttributeInfo::set_YomiOf(valuetype [mscorlib]System.Guid)
0xb55  ldarg.0
0xb56  ldstr    aYomiof// "yomiof"
0xb5b  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xb60  brfalse.s loc_B9B
0xb62  ldarg.0
0xb63  ldstr    aYomiof// "yomiof"
0xb68  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xb6d  ldstr    aNone// "none"
0xb72  ldc.i4.5
0xb73  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xb78  brfalse.s loc_B8D
0xb7a  ldloc.1
0xb7b  ldarg.0
0xb7c  ldstr    aYomiof// "yomiof"
0xb81  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0xb86  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.StringAttributeInfo::set_YomiOf(valuetype [mscorlib]System.Guid)
0xb8b  br.s     loc_B9B
0xb8d  ldarg.1
0xb8e  brfalse.s loc_B9B
0xb90  ldloc.1
0xb91  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb96  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.StringAttributeInfo::set_YomiOf(valuetype [mscorlib]System.Guid)
0xb9b  ldarg.0
0xb9c  ldstr    aSourcetype// "sourcetype"
0xba1  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xba6  brfalse.s loc_BB4
0xba8  ldloc.1
0xba9  ldarg.0
0xbaa  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDataSourceType Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDataSourceFromParameterBag(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag)
0xbaf  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_SourceType(int32)
0xbb4  ldarg.0
0xbb5  ldstr    aFormuladefinit// "formuladefinition"
0xbba  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xbbf  brfalse.s loc_BD2
0xbc1  ldloc.1
0xbc2  ldarg.0
0xbc3  ldstr    aFormuladefinit// "formuladefinition"
0xbc8  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xbcd  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_FormulaDefinition(string)
0xbd2  ldloc.1
0xbd3  ret
```
