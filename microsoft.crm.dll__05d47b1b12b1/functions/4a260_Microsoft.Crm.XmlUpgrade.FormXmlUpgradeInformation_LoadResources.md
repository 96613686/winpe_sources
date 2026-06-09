# Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::LoadResources

- ea: `0x4a260`
- end: `0x4a517`
- name: `Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::LoadResources`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4a220`

## callees

- `0x49fd0`
- `0x49ff0`
- `0x4a010`
- `0x4a240`
- `0x4a260`
- `0x4acc0`

## string_xrefs

- `0x4a267`: `XmlUpgrade/Resources/Resource`
- `0x4a403`: `FunctionMap/Replace`
- `0x4a48c`: `Duplicate <FunctionMap> detected in <Resources><Resource><FunctionMap><Replace> - Resource: {0}, Replace: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x4a260  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.Resource>::.ctor()
0x4a265  stloc.0
0x4a266  ldarg.0
0x4a267  ldstr    aXmlupgradeReso// "XmlUpgrade/Resources/Resource"
0x4a26c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x4a271  call     T0x2B000047
0x4a276  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml]System.Xml.XmlElement>::GetEnumerator()
0x4a27b  stloc.1
0x4a27c  br       loc_4A4FE
0x4a281  ldloc.1
0x4a282  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml]System.Xml.XmlElement>::get_Current()
0x4a287  stloc.2
0x4a288  ldloc.2
0x4a289  ldstr    aWebresourceid_0// "WebResourceId"
0x4a28e  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x4a293  stloc.3
0x4a294  ldloc.2
0x4a295  ldstr    aOldresourcenam// "OldResourceName"
0x4a29a  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x4a29f  stloc.s  4
0x4a2a1  ldloc.2
0x4a2a2  ldstr    aKeep// "Keep"
0x4a2a7  ldc.i4.0
0x4a2a8  call     T0x2B000048
0x4a2ad  stloc.s  5
0x4a2af  ldstr    aOldresourcenam// "OldResourceName"
0x4a2b4  ldloc.s  4
0x4a2b6  call     void Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::ThrowIfNullOrWhitespace(string label, string value)
0x4a2bb  ldloc.s  4
0x4a2bd  callvirt instance string [mscorlib]System.String::ToLower()
0x4a2c2  stloc.s  6
0x4a2c4  ldloc.0
0x4a2c5  ldloc.s  6
0x4a2c7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.Resource>::ContainsKey(var<u1>)
0x4a2cc  brfalse.s loc_4A2E0
0x4a2ce  ldstr    aDuplicateResou// "Duplicate <Resource> detected in <Resou"...
0x4a2d3  ldloc.s  4
0x4a2d5  call     string [mscorlib]System.String::Format(string, object)
0x4a2da  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x4a2df  throw
0x4a2e0  newobj   instance void Microsoft.Crm.XmlUpgrade.Resource::.ctor()
0x4a2e5  dup
0x4a2e6  ldloc.s  4
0x4a2e8  stfld    string Microsoft.Crm.XmlUpgrade.Resource::ResourceName
0x4a2ed  dup
0x4a2ee  ldloc.3
0x4a2ef  stfld    string Microsoft.Crm.XmlUpgrade.Resource::WebResourceId
0x4a2f4  dup
0x4a2f5  ldloc.s  5
0x4a2f7  stfld    bool Microsoft.Crm.XmlUpgrade.Resource::Keep
0x4a2fc  stloc.s  7
0x4a2fe  ldloc.0
0x4a2ff  ldloc.s  6
0x4a301  ldloc.s  7
0x4a303  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.Resource>::Add(var<u1>, !!T0)
0x4a308  ldloc.2
0x4a309  ldstr    aAdd// "Add"
0x4a30e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x4a313  call     T0x2B000047
0x4a318  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml]System.Xml.XmlElement>::GetEnumerator()
0x4a31d  stloc.s  8
0x4a31f  br       loc_4A3E8
0x4a324  ldloc.s  8
0x4a326  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml]System.Xml.XmlElement>::get_Current()
0x4a32b  dup
0x4a32c  ldstr    aWebresourceid_0// "WebResourceId"
0x4a331  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x4a336  stloc.s  9
0x4a338  dup
0x4a339  ldstr    aResourcename// "ResourceName"
0x4a33e  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x4a343  stloc.s  0xA
0x4a345  dup
0x4a346  ldstr    aType// "Type"
0x4a34b  ldstr    aWebresource_0// "WebResource"
0x4a350  call     T0x2B000049
0x4a355  call     valuetype ResourceType Microsoft.Crm.XmlUpgrade.ParserExtensions::ToResourceType(string value)
0x4a35a  stloc.s  0xB
0x4a35c  ldstr    aLibraryuniquei// "LibraryUniqueId"
0x4a361  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x4a366  stloc.s  0xE
0x4a368  ldloca.s 0xE
0x4a36a  constrained. [mscorlib]System.Guid
0x4a370  callvirt instance string [mscorlib]System.Object::ToString()
0x4a375  call     T0x2B000049
0x4a37a  stloc.s  0xC
0x4a37c  ldstr    aResourcename// "ResourceName"
0x4a381  ldloc.s  0xA
0x4a383  call     void Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::ThrowIfNullOrWhitespace(string label, string value)
0x4a388  ldloc.s  0xA
0x4a38a  callvirt instance string [mscorlib]System.String::ToLower()
0x4a38f  stloc.s  0xD
0x4a391  ldloc.s  7
0x4a393  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.ResourceDefinition> Microsoft.Crm.XmlUpgrade.Resource::NewResources
0x4a398  ldloc.s  0xD
0x4a39a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.ResourceDefinition>::ContainsKey(var<u1>)
0x4a39f  brfalse.s loc_4A3B5
0x4a3a1  ldstr    aDuplicateResou_0// "Duplicate <Resource> detected in <Resou"...
0x4a3a6  ldloc.s  4
0x4a3a8  ldloc.s  0xA
0x4a3aa  call     string [mscorlib]System.String::Format(string, object, object)
0x4a3af  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x4a3b4  throw
0x4a3b5  ldloc.s  7
0x4a3b7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.ResourceDefinition> Microsoft.Crm.XmlUpgrade.Resource::NewResources
0x4a3bc  ldloc.s  0xD
0x4a3be  newobj   instance void Microsoft.Crm.XmlUpgrade.ResourceDefinition::.ctor()
0x4a3c3  dup
0x4a3c4  ldloc.s  0xA
0x4a3c6  stfld    string Microsoft.Crm.XmlUpgrade.ResourceDefinition::Name
0x4a3cb  dup
0x4a3cc  ldloc.s  0xB
0x4a3ce  stfld    valuetype ResourceType Microsoft.Crm.XmlUpgrade.ResourceDefinition::Type
0x4a3d3  dup
0x4a3d4  ldloc.s  0xC
0x4a3d6  stfld    string Microsoft.Crm.XmlUpgrade.ResourceDefinition::LibraryUniqueId
0x4a3db  dup
0x4a3dc  ldloc.s  9
0x4a3de  stfld    string Microsoft.Crm.XmlUpgrade.ResourceDefinition::WebResourceId
0x4a3e3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.ResourceDefinition>::Add(var<u1>, !!T0)
0x4a3e8  ldloc.s  8
0x4a3ea  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a3ef  brtrue   loc_4A324
0x4a3f4  leave.s  loc_4A402
0x4a3f6  ldloc.s  8
0x4a3f8  brfalse.s loc_4A401
0x4a3fa  ldloc.s  8
0x4a3fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a401  endfinally
0x4a402  ldloc.2
0x4a403  ldstr    aFunctionmapRep// "FunctionMap/Replace"
0x4a408  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x4a40d  call     T0x2B000047
0x4a412  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml]System.Xml.XmlElement>::GetEnumerator()
0x4a417  stloc.s  8
0x4a419  br       loc_4A4E4
0x4a41e  ldloc.s  8
0x4a420  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml]System.Xml.XmlElement>::get_Current()
0x4a425  dup
0x4a426  ldstr    aOldfunctionnam// "OldFunctionName"
0x4a42b  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x4a430  stloc.s  0xF
0x4a432  dup
0x4a433  ldstr    aNewfunctionnam// "NewFunctionName"
0x4a438  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x4a43d  stloc.s  0x10
0x4a43f  dup
0x4a440  ldstr    aNewresourcenam// "NewResourceName"
0x4a445  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x4a44a  stloc.s  0x11
0x4a44c  ldstr    aPassexecutionc// "PassExecutionContext"
0x4a451  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x4a456  stloc.s  0x12
0x4a458  ldstr    aOldfunctionnam// "OldFunctionName"
0x4a45d  ldloc.s  0xF
0x4a45f  call     void Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::ThrowIfNullOrWhitespace(string label, string value)
0x4a464  ldstr    aNewfunctionnam// "NewFunctionName"
0x4a469  ldloc.s  0x10
0x4a46b  call     void Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::ThrowIfNullOrWhitespace(string label, string value)
0x4a470  ldstr    aNewresourcenam// "NewResourceName"
0x4a475  ldloc.s  0x11
0x4a477  call     void Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::ThrowIfNullOrWhitespace(string label, string value)
0x4a47c  ldloc.s  7
0x4a47e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.FunctionDefinition> Microsoft.Crm.XmlUpgrade.Resource::FunctionMap
0x4a483  ldloc.s  0xF
0x4a485  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.FunctionDefinition>::ContainsKey(var<u1>)
0x4a48a  brfalse.s loc_4A4A0
0x4a48c  ldstr    aDuplicateFunct// "Duplicate <FunctionMap> detected in <Re"...
0x4a491  ldloc.s  4
0x4a493  ldloc.s  0xF
0x4a495  call     string [mscorlib]System.String::Format(string, object, object)
0x4a49a  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x4a49f  throw
0x4a4a0  newobj   instance void Microsoft.Crm.XmlUpgrade.FunctionDefinition::.ctor()
0x4a4a5  stloc.s  0x13
0x4a4a7  ldloc.s  0x13
0x4a4a9  ldloc.s  0xF
0x4a4ab  stfld    string Microsoft.Crm.XmlUpgrade.FunctionDefinition::OldFunctionName
0x4a4b0  ldloc.s  0x13
0x4a4b2  ldloc.s  0x10
0x4a4b4  stfld    string Microsoft.Crm.XmlUpgrade.FunctionDefinition::NewFunctionName
0x4a4b9  ldloc.s  0x13
0x4a4bb  ldloc.s  4
0x4a4bd  stfld    string Microsoft.Crm.XmlUpgrade.FunctionDefinition::OldResourceName
0x4a4c2  ldloc.s  0x13
0x4a4c4  ldloc.s  0x11
0x4a4c6  stfld    string Microsoft.Crm.XmlUpgrade.FunctionDefinition::NewResourceName
0x4a4cb  ldloc.s  0x13
0x4a4cd  ldloc.s  0x12
0x4a4cf  stfld    string Microsoft.Crm.XmlUpgrade.FunctionDefinition::PassExecutionContext
0x4a4d4  ldloc.s  7
0x4a4d6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.FunctionDefinition> Microsoft.Crm.XmlUpgrade.Resource::FunctionMap
0x4a4db  ldloc.s  0xF
0x4a4dd  ldloc.s  0x13
0x4a4df  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.FunctionDefinition>::Add(var<u1>, !!T0)
0x4a4e4  ldloc.s  8
0x4a4e6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a4eb  brtrue   loc_4A41E
0x4a4f0  leave.s  loc_4A4FE
0x4a4f2  ldloc.s  8
0x4a4f4  brfalse.s loc_4A4FD
0x4a4f6  ldloc.s  8
0x4a4f8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a4fd  endfinally
0x4a4fe  ldloc.1
0x4a4ff  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a504  brtrue   loc_4A281
0x4a509  leave.s  loc_4A515
0x4a50b  ldloc.1
0x4a50c  brfalse.s loc_4A514
0x4a50e  ldloc.1
0x4a50f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a514  endfinally
0x4a515  ldloc.0
0x4a516  ret
```
