# Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::ReadReferenceData

- ea: `0x2e580`
- end: `0x2e6a9`
- name: `Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::ReadReferenceData`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2e4c0`

## callees

- `0x2e580`
- `0x2e6b0`
- `0x2eb60`
- `0x2ede0`
- `0x2edf0`

## string_xrefs

- `0x2e5c0`: `ConfigSettings`
- `0x2e60a`: `ConfigSettings`
- `0x2e5d1`: `Reference file does not contain a Default ConfigSettings Element`

## pseudocode

```c

```

## disassembly

```asm
0x2e580  ldarg.0
0x2e581  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [System.Xml.Linq]System.Xml.Linq.XDocument::Parse(string)
0x2e586  dup
0x2e587  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XDocument::get_Root()
0x2e58c  ldstr    aEnvironment// "Environment"
0x2e591  ldstr    aDefault// "Default"
0x2e596  call     class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::GetEntityElement(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string entityType, string entityName)
0x2e59b  dup
0x2e59c  ldstr    aReferenceFileD// "Reference file does not contain a Defau"...
0x2e5a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e5a6  ldstr    aGeo// "Geo"
0x2e5ab  ldstr    aDefault// "Default"
0x2e5b0  call     class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::GetEntityElement(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string entityType, string entityName)
0x2e5b5  dup
0x2e5b6  ldstr    aReferenceFileD_0// "Reference file does not contain a Defau"...
0x2e5bb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e5c0  ldstr    aConfigsettings// "ConfigSettings"
0x2e5c5  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x2e5ca  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x2e5cf  stloc.0
0x2e5d0  ldloc.0
0x2e5d1  ldstr    aReferenceFileD_1// "Reference file does not contain a Defau"...
0x2e5d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e5db  dup
0x2e5dc  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XDocument::get_Root()
0x2e5e1  ldstr    aEnvironment// "Environment"
0x2e5e6  ldarg.1
0x2e5e7  call     class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::GetEntityElement(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string entityType, string entityName)
0x2e5ec  dup
0x2e5ed  ldstr    aReferenceFileD_2// "Reference file does not contain the spe"...
0x2e5f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e5f7  ldstr    aGeo// "Geo"
0x2e5fc  ldarg.2
0x2e5fd  call     class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::GetEntityElement(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string entityType, string entityName)
0x2e602  stloc.1
0x2e603  ldloc.1
0x2e604  brtrue.s loc_2E609
0x2e606  ldnull
0x2e607  br.s     loc_2E619
0x2e609  ldloc.1
0x2e60a  ldstr    aConfigsettings// "ConfigSettings"
0x2e60f  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x2e614  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x2e619  stloc.2
0x2e61a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Admin.AdminService.SettingValueReference>>::.ctor()
0x2e61f  stloc.3
0x2e620  ldloc.0
0x2e621  ldloc.3
0x2e622  ldnull
0x2e623  call     void Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::ReadConfigSettings(class [System.Xml.Linq]System.Xml.Linq.XElement configSettingsElement, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Admin.AdminService.SettingValueReference>> referencesDictionary, [opt] string datacenterName)
0x2e628  ldloc.2
0x2e629  brfalse.s loc_2E633
0x2e62b  ldloc.2
0x2e62c  ldloc.3
0x2e62d  ldarg.3
0x2e62e  call     void Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::ReadConfigSettings(class [System.Xml.Linq]System.Xml.Linq.XElement configSettingsElement, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Admin.AdminService.SettingValueReference>> referencesDictionary, [opt] string datacenterName)
0x2e633  ldloc.3
0x2e634  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Admin.AdminService.SettingValueReference>>, string> <>c::<>9__2_0
0x2e639  dup
0x2e63a  brtrue.s loc_2E653
0x2e63c  pop
0x2e63d  ldsfld   class <>c <>c::<>9
0x2e642  ldftn    instance string <>c::<ReadReferenceData>b__2_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Admin.AdminService.SettingValueReference>> t)
0x2e648  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Admin.AdminService.SettingValueReference>>, string>::.ctor(object, native int)
0x2e64d  dup
0x2e64e  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Admin.AdminService.SettingValueReference>>, string> <>c::<>9__2_0
0x2e653  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Admin.AdminService.SettingValueReference>>, class Microsoft.Crm.Admin.AdminService.SettingValueDiscrepancyCollection> <>c::<>9__2_1
0x2e658  dup
0x2e659  brtrue.s loc_2E672
0x2e65b  pop
0x2e65c  ldsfld   class <>c <>c::<>9
0x2e661  ldftn    instance class Microsoft.Crm.Admin.AdminService.SettingValueDiscrepancyCollection <>c::<ReadReferenceData>b__2_1(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Admin.AdminService.SettingValueReference>> t)
0x2e667  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Admin.AdminService.SettingValueReference>>, class Microsoft.Crm.Admin.AdminService.SettingValueDiscrepancyCollection>::.ctor(object, native int)
0x2e66c  dup
0x2e66d  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Admin.AdminService.SettingValueReference>>, class Microsoft.Crm.Admin.AdminService.SettingValueDiscrepancyCollection> <>c::<>9__2_1
0x2e672  call     T0x2B0000A3
0x2e677  newobj   instance void Microsoft.Crm.Admin.AdminService.SettingsReferenceDescriptor::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Admin.AdminService.SettingValueDiscrepancyCollection> referenceValues)
0x2e67c  stloc.s  4
0x2e67e  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XDocument::get_Root()
0x2e683  ldstr    aBuild// "build"
0x2e688  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x2e68d  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x2e692  stloc.s  5
0x2e694  ldloc.s  5
0x2e696  brfalse.s loc_2E6A6
0x2e698  ldloc.s  4
0x2e69a  ldloc.s  5
0x2e69c  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x2e6a1  callvirt instance void Microsoft.Crm.Admin.AdminService.SettingsReferenceDescriptor::set_ReferenceVersion(string value)
0x2e6a6  ldloc.s  4
0x2e6a8  ret
```
