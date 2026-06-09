# Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::AreSettingValuesEqual

- ea: `0x2e9c0`
- end: `0x2ead5`
- name: `Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::AreSettingValuesEqual`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2e880`

## callees

- `0x2e9c0`
- `0x2ec60`
- `0x2efe0`
- `0x2f000`

## string_xrefs

- `0x2ea7e`: `<?xml`
- `0x2ea91`: `<?xml`

## pseudocode

```c

```

## disassembly

```asm
0x2e9c0  ldarg.0
0x2e9c1  brtrue.s loc_2E9CF
0x2e9c3  ldarg.1
0x2e9c4  callvirt instance string Microsoft.Crm.Admin.AdminService.SettingValueReference::get_ExpectedValue()
0x2e9c9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e9ce  ret
0x2e9cf  ldarg.0
0x2e9d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e9d5  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x2e9da  stloc.0
0x2e9db  ldc.i4.4
0x2e9dc  stloc.1
0x2e9dd  ldarg.1
0x2e9de  callvirt instance valuetype Microsoft.Crm.Admin.AdminService.SettingHandlingType Microsoft.Crm.Admin.AdminService.SettingValueReference::get_HandlingType()
0x2e9e3  stloc.3
0x2e9e4  ldloc.3
0x2e9e5  brfalse.s loc_2E9EF
0x2e9e7  ldloc.3
0x2e9e8  ldc.i4.1
0x2e9e9  bne.un.s loc_2E9F3
0x2e9eb  ldc.i4.5
0x2e9ec  stloc.1
0x2e9ed  br.s     loc_2EA17
0x2e9ef  ldc.i4.4
0x2e9f0  stloc.1
0x2e9f1  br.s     loc_2EA17
0x2e9f3  ldstr    aSettinghandlin// "SettingHandlingType not recognized or s"...
0x2e9f8  ldarg.1
0x2e9f9  callvirt instance valuetype Microsoft.Crm.Admin.AdminService.SettingHandlingType Microsoft.Crm.Admin.AdminService.SettingValueReference::get_HandlingType()
0x2e9fe  stloc.3
0x2e9ff  ldloca.s 3
0x2ea01  constrained. Microsoft.Crm.Admin.AdminService.SettingHandlingType
0x2ea07  callvirt instance string [mscorlib]System.Object::ToString()
0x2ea0c  call     string [mscorlib]System.String::Concat(string, string)
0x2ea11  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string)
0x2ea16  throw
0x2ea17  ldloc.0
0x2ea18  ldarg.1
0x2ea19  callvirt instance string Microsoft.Crm.Admin.AdminService.SettingValueReference::get_ExpectedValue()
0x2ea1e  ldloc.1
0x2ea1f  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2ea24  stloc.2
0x2ea25  ldloc.2
0x2ea26  brtrue   loc_2EAD3
0x2ea2b  ldarg.0
0x2ea2c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2ea31  ldtoken  [mscorlib]System.Boolean
0x2ea36  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ea3b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2ea40  brfalse.s loc_2EA7D
0x2ea42  ldarg.0
0x2ea43  unbox.any [mscorlib]System.Boolean
0x2ea48  stloc.s  4
0x2ea4a  ldloc.s  4
0x2ea4c  brfalse.s loc_2EA60
0x2ea4e  ldarg.1
0x2ea4f  callvirt instance string Microsoft.Crm.Admin.AdminService.SettingValueReference::get_ExpectedValue()
0x2ea54  ldstr    a1// "1"
0x2ea59  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ea5e  brtrue.s loc_2EA79
0x2ea60  ldloc.s  4
0x2ea62  brtrue.s loc_2EA76
0x2ea64  ldarg.1
0x2ea65  callvirt instance string Microsoft.Crm.Admin.AdminService.SettingValueReference::get_ExpectedValue()
0x2ea6a  ldstr    a0_0// "0"
0x2ea6f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ea74  br.s     loc_2EA7A
0x2ea76  ldc.i4.0
0x2ea77  br.s     loc_2EA7A
0x2ea79  ldc.i4.1
0x2ea7a  stloc.2
0x2ea7b  br.s     loc_2EAD3
0x2ea7d  ldloc.0
0x2ea7e  ldstr    aXml_0// "<?xml"
0x2ea83  ldc.i4.4
0x2ea84  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2ea89  brfalse.s loc_2EAD3
0x2ea8b  ldarg.1
0x2ea8c  callvirt instance string Microsoft.Crm.Admin.AdminService.SettingValueReference::get_ExpectedValue()
0x2ea91  ldstr    aXml_0// "<?xml"
0x2ea96  ldc.i4.4
0x2ea97  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2ea9c  brfalse.s loc_2EAD3
0x2ea9e  ldloc.0
0x2ea9f  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [System.Xml.Linq]System.Xml.Linq.XDocument::Parse(string)
0x2eaa4  stloc.s  5
0x2eaa6  ldarg.1
0x2eaa7  callvirt instance string Microsoft.Crm.Admin.AdminService.SettingValueReference::get_ExpectedValue()
0x2eaac  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [System.Xml.Linq]System.Xml.Linq.XDocument::Parse(string)
0x2eab1  ldloc.s  5
0x2eab3  call     string Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::XDocumentToString(class [System.Xml.Linq]System.Xml.Linq.XDocument doc)
0x2eab8  stloc.s  6
0x2eaba  call     string Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::XDocumentToString(class [System.Xml.Linq]System.Xml.Linq.XDocument doc)
0x2eabf  stloc.s  7
0x2eac1  ldloc.s  6
0x2eac3  ldloc.s  7
0x2eac5  ldloc.1
0x2eac6  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2eacb  stloc.2
0x2eacc  leave.s  loc_2EAD3
0x2eace  pop
0x2eacf  ldc.i4.0
0x2ead0  stloc.2
0x2ead1  leave.s  loc_2EAD3
0x2ead3  ldloc.2
0x2ead4  ret
```
