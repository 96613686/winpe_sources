# Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::.ctor

- ea: `0x4af30`
- end: `0x4b0e0`
- name: `Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::.ctor`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4af10`

## callees

- `0x190a0`
- `0x4af30`
- `0x4b240`
- `0x4b2a0`

## string_xrefs

- `0x4af70`: `Command`
- `0x4af57`: `RibbonCommandsBackTrackTable.xml`

## pseudocode

```c

```

## disassembly

```asm
0x4af30  ldarg.0
0x4af31  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod>::.ctor()
0x4af36  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod> Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::_backTrackCommands
0x4af3b  ldarg.0
0x4af3c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod>::.ctor()
0x4af41  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod> Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::_upgradableCommands
0x4af46  ldarg.0
0x4af47  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4af4c  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::_multiMappingComands
0x4af51  ldarg.0
0x4af52  call     instance void [mscorlib]System.Object::.ctor()
0x4af57  ldstr    aRibboncommands// "RibbonCommandsBackTrackTable.xml"
0x4af5c  call     string Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath(string fileId)
0x4af61  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::LoadXmlDocumentFromFile(string)
0x4af66  newobj   instance void [System.Xml]System.Xml.XmlNodeReader::.ctor(class [System.Xml]System.Xml.XmlNode)
0x4af6b  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Load(class [System.Xml]System.Xml.XmlReader)
0x4af70  ldstr    aCommand// "Command"
0x4af75  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x4af7a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Elements(class [System.Xml.Linq]System.Xml.Linq.XName)
0x4af7f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x4af84  stloc.0
0x4af85  br       loc_4B0C0
0x4af8a  ldloc.0
0x4af8b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x4af90  dup
0x4af91  ldstr    aEntityname_0// "EntityName"
0x4af96  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x4af9b  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x4afa0  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x4afa5  stloc.1
0x4afa6  dup
0x4afa7  ldstr    aOldfunctionnam// "OldFunctionName"
0x4afac  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x4afb1  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x4afb6  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x4afbb  stloc.2
0x4afbc  dup
0x4afbd  ldstr    aOldlibrary// "OldLibrary"
0x4afc2  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x4afc7  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x4afcc  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x4afd1  stloc.3
0x4afd2  dup
0x4afd3  ldstr    aNewfunctionnam// "NewFunctionName"
0x4afd8  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x4afdd  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x4afe2  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x4afe7  stloc.s  4
0x4afe9  dup
0x4afea  ldstr    aNewlibrary// "NewLibrary"
0x4afef  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x4aff4  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x4aff9  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x4affe  stloc.s  5
0x4b000  ldstr    aIntroducedvers// "IntroducedVersion"
0x4b005  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x4b00a  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x4b00f  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x4b014  stloc.s  6
0x4b016  ldarg.0
0x4b017  ldloc.s  4
0x4b019  ldloc.s  5
0x4b01b  call     instance string Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::GenerateKey(string function, string library)
0x4b020  stloc.s  7
0x4b022  ldarg.0
0x4b023  ldloc.2
0x4b024  ldloc.3
0x4b025  call     instance string Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::GenerateKey(string function, string library)
0x4b02a  stloc.s  8
0x4b02c  ldarg.0
0x4b02d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod> Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::_backTrackCommands
0x4b032  ldloc.s  7
0x4b034  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod>::ContainsKey(var<u1>)
0x4b039  brfalse.s loc_4B058
0x4b03b  ldarg.0
0x4b03c  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::_multiMappingComands
0x4b041  ldloc.s  7
0x4b043  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4b048  ldarg.0
0x4b049  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod> Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::_backTrackCommands
0x4b04e  ldloc.s  7
0x4b050  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod>::Remove(var<u1>)
0x4b055  pop
0x4b056  br.s     loc_4B0C0
0x4b058  ldarg.0
0x4b059  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::_multiMappingComands
0x4b05e  ldloc.s  7
0x4b060  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x4b065  brtrue.s loc_4B082
0x4b067  ldarg.0
0x4b068  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod> Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::_backTrackCommands
0x4b06d  ldloc.s  7
0x4b06f  ldloc.1
0x4b070  ldloc.2
0x4b071  ldloc.3
0x4b072  ldloc.s  4
0x4b074  ldloc.s  5
0x4b076  ldloc.s  6
0x4b078  newobj   instance void Microsoft.Crm.Utils.Ribbon.BacktrackMethod::.ctor(string entityName, string oldFunctionName, string oldLibrary, string newFunctionName, string newLibrary, string introducedVersion)
0x4b07d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod>::Add(var<u1>, !!T0)
0x4b082  ldarg.0
0x4b083  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod> Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::_upgradableCommands
0x4b088  ldloc.s  8
0x4b08a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod>::ContainsKey(var<u1>)
0x4b08f  brtrue.s loc_4B0AE
0x4b091  ldarg.0
0x4b092  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod> Microsoft.Crm.Utils.Ribbon.RibbonCommandsBackTrackTable::_upgradableCommands
0x4b097  ldloc.s  8
0x4b099  ldloc.1
0x4b09a  ldloc.2
0x4b09b  ldloc.3
0x4b09c  ldloc.s  4
0x4b09e  ldloc.s  5
0x4b0a0  ldloc.s  6
0x4b0a2  newobj   instance void Microsoft.Crm.Utils.Ribbon.BacktrackMethod::.ctor(string entityName, string oldFunctionName, string oldLibrary, string newFunctionName, string newLibrary, string introducedVersion)
0x4b0a7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Utils.Ribbon.BacktrackMethod>::Add(var<u1>, !!T0)
0x4b0ac  br.s     loc_4B0C0
0x4b0ae  ldstr    aDuplicateRibbo// "Duplicate ribbon backtrack entry is not"...
0x4b0b3  ldloc.2
0x4b0b4  ldloc.3
0x4b0b5  call     string [mscorlib]System.String::Format(string, object, object)
0x4b0ba  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4b0bf  throw
0x4b0c0  ldloc.0
0x4b0c1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4b0c6  brtrue   loc_4AF8A
0x4b0cb  leave.s  loc_4B0D7
0x4b0cd  ldloc.0
0x4b0ce  brfalse.s loc_4B0D6
0x4b0d0  ldloc.0
0x4b0d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4b0d6  endfinally
0x4b0d7  leave.s  loc_4B0DF
0x4b0d9  pop
0x4b0da  leave.s  loc_4B0DF
0x4b0dc  pop
0x4b0dd  leave.s  loc_4B0DF
0x4b0df  ret
```
