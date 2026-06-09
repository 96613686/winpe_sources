# Microsoft.Crm.Sdk.Metadata.MetadataConverter::ValidateAttributeTypeForCreate

- ea: `0x8c50`
- end: `0x8d8d`
- name: `Microsoft.Crm.Sdk.Metadata.MetadataConverter::ValidateAttributeTypeForCreate`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8be0`

## callees

- `0x8c50`

## string_xrefs

- `0x8c5c`: `Attribute of type {0} cannot be created through the SDK`
- `0x8ce9`: `Attribute of type {0} with format {1} cannot be created through the SDK`

## pseudocode

```c

```

## disassembly

```asm
0x8c50  ldarg.0
0x8c51  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x8c56  stloc.0
0x8c57  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8c5c  ldstr    aAttributeOfTyp// "Attribute of type {0} cannot be created"...
0x8c61  ldc.i4.1
0x8c62  newarr   [mscorlib]System.Object
0x8c67  dup
0x8c68  ldc.i4.0
0x8c69  ldloc.0
0x8c6a  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x8c6f  stelem.ref
0x8c70  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8c75  stloc.1
0x8c76  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type> Microsoft.Crm.Sdk.Metadata.MetadataConverter::_allowedMetadataTypes
0x8c7b  ldloc.0
0x8c7c  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Contains(var<u1>)
0x8c81  brtrue.s loc_8C8A
0x8c83  ldloc.1
0x8c84  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x8c89  throw
0x8c8a  ldloc.0
0x8c8b  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringAttributeMetadata
0x8c90  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8c95  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x8c9a  brfalse.s loc_8D13
0x8c9c  ldarg.0
0x8c9d  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringAttributeMetadata
0x8ca2  stloc.2
0x8ca3  ldloc.2
0x8ca4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormatName [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringAttributeMetadata::get_FormatName()
0x8ca9  ldnull
0x8caa  call     bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormatName::op_Inequality(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormatName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormatName)
0x8caf  brfalse.s loc_8CC3
0x8cb1  ldloc.2
0x8cb2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormatName [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringAttributeMetadata::get_FormatName()
0x8cb7  ldsfld   class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormatName [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormatName::VersionNumber
0x8cbc  call     bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormatName::op_Equality(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormatName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormatName)
0x8cc1  brtrue.s loc_8CE4
0x8cc3  ldloc.2
0x8cc4  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormat> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringAttributeMetadata::get_Format()
0x8cc9  stloc.3
0x8cca  ldloca.s 3
0x8ccc  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormat>::get_HasValue()
0x8cd1  brfalse.s loc_8D13
0x8cd3  ldloc.2
0x8cd4  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormat> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringAttributeMetadata::get_Format()
0x8cd9  stloc.3
0x8cda  ldloca.s 3
0x8cdc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormat>::get_Value()
0x8ce1  ldc.i4.6
0x8ce2  bne.un.s loc_8D13
0x8ce4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8ce9  ldstr    aAttributeOfTyp_0// "Attribute of type {0} with format {1} c"...
0x8cee  ldc.i4.2
0x8cef  newarr   [mscorlib]System.Object
0x8cf4  dup
0x8cf5  ldc.i4.0
0x8cf6  ldloc.0
0x8cf7  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x8cfc  stelem.ref
0x8cfd  dup
0x8cfe  ldc.i4.1
0x8cff  ldc.i4.6
0x8d00  box      [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringFormat
0x8d05  stelem.ref
0x8d06  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8d0b  stloc.1
0x8d0c  ldloc.1
0x8d0d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x8d12  throw
0x8d13  ldloc.0
0x8d14  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MultiSelectPicklistAttributeMetadata
0x8d19  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8d1e  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x8d23  brfalse.s loc_8D43
0x8d25  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x8d2a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x8d2f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MultiSelectOptionSet()
0x8d34  ldarg.1
0x8d35  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8d3a  brtrue.s loc_8D43
0x8d3c  ldloc.1
0x8d3d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x8d42  throw
0x8d43  ldarg.0
0x8d44  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_AutoNumberFormat()
0x8d49  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8d4e  brtrue.s loc_8D8C
0x8d50  ldloc.0
0x8d51  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringAttributeMetadata
0x8d56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8d5b  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x8d60  brfalse.s loc_8D8C
0x8d62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8d67  ldstr    aAttribute0With// "Attribute {0} with type {1} has AutoNum"...
0x8d6c  ldc.i4.2
0x8d6d  newarr   [mscorlib]System.Object
0x8d72  dup
0x8d73  ldc.i4.0
0x8d74  ldloc.0
0x8d75  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x8d7a  stelem.ref
0x8d7b  dup
0x8d7c  ldc.i4.1
0x8d7d  ldloc.0
0x8d7e  stelem.ref
0x8d7f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8d84  stloc.1
0x8d85  ldloc.1
0x8d86  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x8d8b  throw
0x8d8c  ret
```
