# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetMapXmlNode

- ea: `0x5980`
- end: `0x5a14`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetMapXmlNode`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4b50`
- `0x4ea0`

## callees

- `0x5980`

## pseudocode

```c

```

## disassembly

```asm
0x5980  ldarg.2
0x5981  ldstr    aSourceentityna// "sourceentityname"
0x5986  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x598b  castclass [mscorlib]System.String
0x5990  stloc.0
0x5991  ldarg.1
0x5992  ldstr    aMapEntitymapsE// "/Map/EntityMaps/EntityMap[not(@Unused)]"
0x5997  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x599c  stloc.1
0x599d  ldloc.1
0x599e  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x59a3  stloc.2
0x59a4  br.s     loc_59E7
0x59a6  ldloc.2
0x59a7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x59ac  castclass [System.Xml]System.Xml.XmlNode
0x59b1  stloc.3
0x59b2  ldloc.3
0x59b3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x59b8  ldstr    aSourceentityna_0// "SourceEntityName"
0x59bd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x59c2  brfalse.s loc_59E7
0x59c4  ldloc.3
0x59c5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x59ca  ldstr    aSourceentityna_0// "SourceEntityName"
0x59cf  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x59d4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x59d9  ldloc.0
0x59da  ldc.i4.5
0x59db  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x59e0  brfalse.s loc_59E7
0x59e2  ldloc.3
0x59e3  stloc.s  4
0x59e5  leave.s  loc_5A11
0x59e7  ldloc.2
0x59e8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59ed  brtrue.s loc_59A6
0x59ef  leave.s  loc_5A0F
0x59f1  ldloc.2
0x59f2  isinst   [mscorlib]System.IDisposable
0x59f7  stloc.s  5
0x59f9  ldloc.s  5
0x59fb  brfalse.s loc_5A04
0x59fd  ldloc.s  5
0x59ff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a04  endfinally
0x5a05  ldloc.1
0x5a06  brfalse.s loc_5A0E
0x5a08  ldloc.1
0x5a09  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a0e  endfinally
0x5a0f  ldnull
0x5a10  ret
0x5a11  ldloc.s  4
0x5a13  ret
```
