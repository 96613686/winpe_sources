# Microsoft.Crm.Metadata.ManagedPropertyDescription::FillPropertiesFromXml_0

- ea: `0x397e0`
- end: `0x39a22`
- name: `Microsoft.Crm.Metadata.ManagedPropertyDescription::FillPropertiesFromXml_0`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbc40`
- `0xbc50`
- `0xbc80`
- `0x397e0`
- `0x39a50`
- `0x39a90`
- `0x39ab0`
- `0x39ad0`
- `0x39af0`
- `0x39b10`
- `0x39b30`
- `0x39b50`
- `0x39b70`
- `0x39b90`
- `0x39bb0`
- `0x39bd0`
- `0x39c30`

## string_xrefs

- `0x397f2`: `ManagedProperty XML requires the ManagedPropertyId`
- `0x39854`: `ManagedProperty XML requires the LogicalName`

## pseudocode

```c

```

## disassembly

```asm
0x397e0  ldarg.1
0x397e1  ldstr    aManagedpropert_3// "ManagedPropertyId"
0x397e6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x397eb  ldnull
0x397ec  ceq
0x397ee  ldarg.2
0x397ef  and
0x397f0  brfalse.s loc_397FD
0x397f2  ldstr    aManagedpropert_12// "ManagedProperty XML requires the Manage"...
0x397f7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x397fc  throw
0x397fd  ldarg.0
0x397fe  ldarg.1
0x397ff  ldstr    aManagedpropert_3// "ManagedPropertyId"
0x39804  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39809  brfalse.s loc_39822
0x3980b  ldarg.1
0x3980c  ldstr    aManagedpropert_3// "ManagedPropertyId"
0x39811  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39816  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3981b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x39820  br.s     loc_39827
0x39822  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x39827  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_ManagedPropertyId(valuetype [mscorlib]System.Guid value)
0x3982c  ldarg.1
0x3982d  ldstr    aLogicalname// "LogicalName"
0x39832  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39837  brfalse.s loc_39851
0x39839  ldarg.0
0x3983a  ldarg.1
0x3983b  ldstr    aLogicalname// "LogicalName"
0x39840  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39845  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3984a  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_LogicalName(string value)
0x3984f  br.s     loc_3985F
0x39851  ldarg.2
0x39852  brfalse.s loc_3985F
0x39854  ldstr    aManagedpropert_13// "ManagedProperty XML requires the Logica"...
0x39859  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3985e  throw
0x3985f  ldarg.1
0x39860  ldstr    aManagedpropert_4// "ManagedPropertyType"
0x39865  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3986a  brfalse.s loc_39891
0x3986c  ldarg.0
0x3986d  ldtoken  [Microsoft.Crm]Microsoft.Crm.ManagedPropertyType
0x39872  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x39877  ldarg.1
0x39878  ldstr    aManagedpropert_4// "ManagedPropertyType"
0x3987d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39882  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x39887  call     int32 Microsoft.Crm.Platform.ConvertHelper::NonFlagEnumFromXmlString(class [mscorlib]System.Type enumType, string value)
0x3988c  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_ManagedPropertyType(valuetype [Microsoft.Crm]Microsoft.Crm.ManagedPropertyType value)
0x39891  ldarg.1
0x39892  ldstr    aOperation// "Operation"
0x39897  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3989c  brfalse.s loc_398C3
0x3989e  ldarg.0
0x3989f  ldtoken  [Microsoft.Crm]Microsoft.Crm.ManagedPropertyOperations
0x398a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x398a9  ldarg.1
0x398aa  ldstr    aOperation// "Operation"
0x398af  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x398b4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x398b9  call     int32 Microsoft.Crm.Platform.ConvertHelper::NonFlagEnumFromXmlString(class [mscorlib]System.Type enumType, string value)
0x398be  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_Operation(valuetype [Microsoft.Crm]Microsoft.Crm.ManagedPropertyOperations value)
0x398c3  ldarg.1
0x398c4  ldstr    aIsglobalforope// "IsGlobalForOperation"
0x398c9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x398ce  brfalse.s loc_398E6
0x398d0  ldarg.0
0x398d1  ldarg.1
0x398d2  ldstr    aIsglobalforope// "IsGlobalForOperation"
0x398d7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x398dc  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x398e1  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_IsGlobalForOperation(bool value)
0x398e6  ldarg.1
0x398e7  ldstr    aEvaluationprio// "EvaluationPriority"
0x398ec  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x398f1  brfalse.s loc_39918
0x398f3  ldarg.0
0x398f4  ldtoken  [Microsoft.Crm]Microsoft.Crm.ManagedPropertyEvaluationPriority
0x398f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x398fe  ldarg.1
0x398ff  ldstr    aEvaluationprio// "EvaluationPriority"
0x39904  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39909  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3990e  call     int32 Microsoft.Crm.Platform.ConvertHelper::NonFlagEnumFromXmlString(class [mscorlib]System.Type enumType, string value)
0x39913  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_EvaluationPriority(valuetype [Microsoft.Crm]Microsoft.Crm.ManagedPropertyEvaluationPriority value)
0x39918  ldarg.1
0x39919  ldstr    aIsprivate// "IsPrivate"
0x3991e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39923  brfalse.s loc_3993B
0x39925  ldarg.0
0x39926  ldarg.1
0x39927  ldstr    aIsprivate// "IsPrivate"
0x3992c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39931  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x39936  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_IsPrivate(bool value)
0x3993b  ldarg.1
0x3993c  ldstr    aErrorcode// "ErrorCode"
0x39941  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39946  brfalse.s loc_3996D
0x39948  ldarg.0
0x39949  ldarg.1
0x3994a  ldstr    aErrorcode// "ErrorCode"
0x3994f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39954  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x39959  ldc.i4   0x203
0x3995e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39963  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x39968  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_ErrorCode(int32 value)
0x3996d  ldarg.1
0x3996e  ldstr    aEnablesentityn// "EnablesEntityName"
0x39973  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39978  brfalse.s loc_39990
0x3997a  ldarg.0
0x3997b  ldarg.1
0x3997c  ldstr    aEnablesentityn// "EnablesEntityName"
0x39981  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39986  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3998b  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_EnablesEntityName(string value)
0x39990  ldarg.1
0x39991  ldstr    aEnablesattribu// "EnablesAttributeName"
0x39996  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3999b  brfalse.s loc_399B3
0x3999d  ldarg.0
0x3999e  ldarg.1
0x3999f  ldstr    aEnablesattribu// "EnablesAttributeName"
0x399a4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x399a9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x399ae  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_EnablesAttributeName(string value)
0x399b3  ldarg.1
0x399b4  ldstr    aEvaluationcond// "EvaluationConditionClass"
0x399b9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x399be  brfalse.s loc_399D6
0x399c0  ldarg.0
0x399c1  ldarg.1
0x399c2  ldstr    aEvaluationcond// "EvaluationConditionClass"
0x399c7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x399cc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x399d1  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_EvaluationConditionClass(string value)
0x399d6  ldarg.1
0x399d7  ldstr    aEvaluationcond_0// "EvaluationConditionAssembly"
0x399dc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x399e1  brfalse.s loc_399F9
0x399e3  ldarg.0
0x399e4  ldarg.1
0x399e5  ldstr    aEvaluationcond_0// "EvaluationConditionAssembly"
0x399ea  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x399ef  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x399f4  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_EvaluationConditionAssembly(string value)
0x399f9  ldarg.1
0x399fa  ldstr    aIntroducedvers// "IntroducedVersion"
0x399ff  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39a04  brfalse.s loc_39A21
0x39a06  ldarg.0
0x39a07  ldarg.1
0x39a08  ldstr    aIntroducedvers// "IntroducedVersion"
0x39a0d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x39a12  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x39a17  call     class [mscorlib]System.Version Microsoft.Crm.Platform.ConvertHelper::ToVersionFromString(string value)
0x39a1c  callvirt instance void Microsoft.Crm.Metadata.ManagedPropertyDescription::set_IntroducedVersion(class [mscorlib]System.Version value)
0x39a21  ret
```
