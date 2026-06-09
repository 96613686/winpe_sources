# Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::LoadEntities

- ea: `0x4a520`
- end: `0x4a6b3`
- name: `Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::LoadEntities`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x4a220`

## callees

- `0x49fd0`
- `0x4a060`
- `0x4a240`
- `0x4a520`
- `0x4acc0`

## string_xrefs

- `0x4a527`: `XmlUpgrade/Entities/Entity`
- `0x4a644`: `Remove`
- `0x4a65f`: `Duplicate <Resource> detected in <Entities><Entity><Remove> - Entity: {0}, Remove: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x4a520  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.EntityDefinition>::.ctor()
0x4a525  stloc.0
0x4a526  ldarg.0
0x4a527  ldstr    aXmlupgradeEnti// "XmlUpgrade/Entities/Entity"
0x4a52c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x4a531  call     T0x2B000047
0x4a536  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml]System.Xml.XmlElement>::GetEnumerator()
0x4a53b  stloc.1
0x4a53c  br       loc_4A69A
0x4a541  ldloc.1
0x4a542  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml]System.Xml.XmlElement>::get_Current()
0x4a547  dup
0x4a548  ldstr    aName// "Name"
0x4a54d  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x4a552  stloc.2
0x4a553  ldstr    aName// "Name"
0x4a558  ldloc.2
0x4a559  call     void Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::ThrowIfNullOrWhitespace(string label, string value)
0x4a55e  ldloc.0
0x4a55f  ldloc.2
0x4a560  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.EntityDefinition>::ContainsKey(var<u1>)
0x4a565  brfalse.s loc_4A578
0x4a567  ldstr    aDuplicateEntit// "Duplicate <Entity> detected in <Entitie"...
0x4a56c  ldloc.2
0x4a56d  call     string [mscorlib]System.String::Format(string, object)
0x4a572  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x4a577  throw
0x4a578  newobj   instance void Microsoft.Crm.XmlUpgrade.EntityDefinition::.ctor()
0x4a57d  dup
0x4a57e  ldloc.2
0x4a57f  stfld    string Microsoft.Crm.XmlUpgrade.EntityDefinition::EntityName
0x4a584  stloc.3
0x4a585  ldloc.0
0x4a586  ldloc.2
0x4a587  ldloc.3
0x4a588  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.EntityDefinition>::Add(var<u1>, !!T0)
0x4a58d  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x4a592  call     T0x2B000047
0x4a597  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml]System.Xml.XmlElement>::GetEnumerator()
0x4a59c  stloc.s  4
0x4a59e  br       loc_4A680
0x4a5a3  ldloc.s  4
0x4a5a5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml]System.Xml.XmlElement>::get_Current()
0x4a5aa  dup
0x4a5ab  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x4a5b0  stloc.s  5
0x4a5b2  dup
0x4a5b3  ldstr    aResourcename// "ResourceName"
0x4a5b8  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x4a5bd  stloc.s  6
0x4a5bf  ldstr    aType// "Type"
0x4a5c4  ldstr    aWebresource_0// "WebResource"
0x4a5c9  call     T0x2B000049
0x4a5ce  call     valuetype ResourceType Microsoft.Crm.XmlUpgrade.ParserExtensions::ToResourceType(string value)
0x4a5d3  stloc.s  7
0x4a5d5  ldstr    aResourcename// "ResourceName"
0x4a5da  ldloc.s  6
0x4a5dc  call     void Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::ThrowIfNullOrWhitespace(string label, string value)
0x4a5e1  ldloc.s  6
0x4a5e3  callvirt instance string [mscorlib]System.String::ToLower()
0x4a5e8  stloc.s  8
0x4a5ea  newobj   instance void Microsoft.Crm.XmlUpgrade.ResourceDefinition::.ctor()
0x4a5ef  dup
0x4a5f0  ldloc.s  6
0x4a5f2  stfld    string Microsoft.Crm.XmlUpgrade.ResourceDefinition::Name
0x4a5f7  dup
0x4a5f8  ldloc.s  7
0x4a5fa  stfld    valuetype ResourceType Microsoft.Crm.XmlUpgrade.ResourceDefinition::Type
0x4a5ff  stloc.s  9
0x4a601  ldloc.s  5
0x4a603  ldstr    aAdd// "Add"
0x4a608  callvirt instance bool [mscorlib]System.String::Equals(string)
0x4a60d  brfalse.s loc_4A642
0x4a60f  ldloc.3
0x4a610  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.ResourceDefinition> Microsoft.Crm.XmlUpgrade.EntityDefinition::AddResources
0x4a615  ldloc.s  8
0x4a617  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.ResourceDefinition>::ContainsKey(var<u1>)
0x4a61c  brfalse.s loc_4A631
0x4a61e  ldstr    aDuplicateResou_1// "Duplicate <Resource> detected in <Entit"...
0x4a623  ldloc.2
0x4a624  ldloc.s  6
0x4a626  call     string [mscorlib]System.String::Format(string, object, object)
0x4a62b  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x4a630  throw
0x4a631  ldloc.3
0x4a632  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.ResourceDefinition> Microsoft.Crm.XmlUpgrade.EntityDefinition::AddResources
0x4a637  ldloc.s  8
0x4a639  ldloc.s  9
0x4a63b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.ResourceDefinition>::Add(var<u1>, !!T0)
0x4a640  br.s     loc_4A680
0x4a642  ldloc.s  5
0x4a644  ldstr    aRemove// "Remove"
0x4a649  callvirt instance bool [mscorlib]System.String::Equals(string)
0x4a64e  brfalse.s loc_4A680
0x4a650  ldloc.3
0x4a651  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.XmlUpgrade.EntityDefinition::RemoveResources
0x4a656  ldloc.s  8
0x4a658  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x4a65d  brfalse.s loc_4A672
0x4a65f  ldstr    aDuplicateResou_2// "Duplicate <Resource> detected in <Entit"...
0x4a664  ldloc.2
0x4a665  ldloc.s  6
0x4a667  call     string [mscorlib]System.String::Format(string, object, object)
0x4a66c  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x4a671  throw
0x4a672  ldloc.3
0x4a673  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.XmlUpgrade.EntityDefinition::RemoveResources
0x4a678  ldloc.s  8
0x4a67a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x4a67f  pop
0x4a680  ldloc.s  4
0x4a682  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a687  brtrue   loc_4A5A3
0x4a68c  leave.s  loc_4A69A
0x4a68e  ldloc.s  4
0x4a690  brfalse.s loc_4A699
0x4a692  ldloc.s  4
0x4a694  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a699  endfinally
0x4a69a  ldloc.1
0x4a69b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a6a0  brtrue   loc_4A541
0x4a6a5  leave.s  loc_4A6B1
0x4a6a7  ldloc.1
0x4a6a8  brfalse.s loc_4A6B0
0x4a6aa  ldloc.1
0x4a6ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a6b0  endfinally
0x4a6b1  ldloc.0
0x4a6b2  ret
```
