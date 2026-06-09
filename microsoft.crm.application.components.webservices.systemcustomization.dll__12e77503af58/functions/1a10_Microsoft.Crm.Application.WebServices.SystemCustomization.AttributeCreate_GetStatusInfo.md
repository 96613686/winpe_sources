# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetStatusInfo

- ea: `0x1a10`
- end: `0x1b2e`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetStatusInfo`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x1a0`
- `0x1c0`
- `0x200`
- `0x220`
- `0x270`
- `0x370`
- `0x1a10`

## pseudocode

```c

```

## disassembly

```asm
0x1a10  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a15  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1a1a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1a1f  stloc.0
0x1a20  ldloc.0
0x1a21  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.StatusAttributeInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a26  stloc.1
0x1a27  ldarg.0
0x1a28  ldstr    aStates// "states"
0x1a2d  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x1a32  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1a37  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1a3c  stloc.2
0x1a3d  ldstr    aState// "state"
0x1a42  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag[] Microsoft.Crm.Application.WebServices.ParameterBag::GetBagArray(string name)
0x1a47  stloc.3
0x1a48  ldc.i4.0
0x1a49  stloc.s  4
0x1a4b  br       loc_1B22
0x1a50  ldloc.3
0x1a51  ldloc.s  4
0x1a53  ldelem.ref
0x1a54  dup
0x1a55  ldstr    aValue// "value"
0x1a5a  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x1a5f  stloc.s  5
0x1a61  ldstr    aValues// "values"
0x1a66  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x1a6b  ldstr    aValue// "value"
0x1a70  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag[] Microsoft.Crm.Application.WebServices.ParameterBag::GetBagArray(string name)
0x1a75  stloc.s  6
0x1a77  ldc.i4.0
0x1a78  stloc.s  7
0x1a7a  br       loc_1B11
0x1a7f  ldloc.s  6
0x1a81  ldloc.s  7
0x1a83  ldelem.ref
0x1a84  dup
0x1a85  ldstr    aLabel// "label"
0x1a8a  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x1a8f  stloc.s  8
0x1a91  dup
0x1a92  ldstr    aValue// "value"
0x1a97  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x1a9c  stloc.s  9
0x1a9e  dup
0x1a9f  ldstr    aColor// "color"
0x1aa4  ldstr    a0000ff// "#0000ff"
0x1aa9  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x1aae  stloc.s  0xA
0x1ab0  ldloc.2
0x1ab1  ldloc.s  8
0x1ab3  ldloc.0
0x1ab4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ab9  stloc.s  0xB
0x1abb  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0x1ac0  stloc.s  0xC
0x1ac2  ldloc.s  0xC
0x1ac4  ldloc.s  0xB
0x1ac6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x1acb  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0x1ad0  stloc.s  0xD
0x1ad2  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetInnerXml()
0x1ad7  stloc.s  0xE
0x1ad9  ldloc.s  9
0x1adb  ldloc.s  5
0x1add  ldloc.s  0xA
0x1adf  ldloc.s  0xE
0x1ae1  ldloc.s  0xC
0x1ae3  ldloc.s  0xD
0x1ae5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PreloadedEnumOptionMetadataDataProviderFull::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0x1aea  ldloc.0
0x1aeb  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption::.ctor(int32, int32, string, string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionMetadataDataProvider, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1af0  stloc.s  0xF
0x1af2  ldloc.1
0x1af3  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1af8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0x1afd  ldloc.s  0xF
0x1aff  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x1b04  ldloc.s  0xF
0x1b06  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::Add(var<u1>, !!T0)
0x1b0b  ldloc.s  7
0x1b0d  ldc.i4.1
0x1b0e  add
0x1b0f  stloc.s  7
0x1b11  ldloc.s  7
0x1b13  ldloc.s  6
0x1b15  ldlen
0x1b16  conv.i4
0x1b17  blt      loc_1A7F
0x1b1c  ldloc.s  4
0x1b1e  ldc.i4.1
0x1b1f  add
0x1b20  stloc.s  4
0x1b22  ldloc.s  4
0x1b24  ldloc.3
0x1b25  ldlen
0x1b26  conv.i4
0x1b27  blt      loc_1A50
0x1b2c  ldloc.1
0x1b2d  ret
```
