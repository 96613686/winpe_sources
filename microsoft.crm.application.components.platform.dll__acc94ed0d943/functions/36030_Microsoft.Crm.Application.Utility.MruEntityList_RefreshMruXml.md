# Microsoft.Crm.Application.Utility.MruEntityList::RefreshMruXml

- ea: `0x36030`
- end: `0x3610d`
- name: `Microsoft.Crm.Application.Utility.MruEntityList::RefreshMruXml`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x35ed0`

## callees

- `0x35e10`
- `0x36030`
- `0x5be20`
- `0x5be40`

## string_xrefs

- `0x36036`: `insertintoemailmruxml`
- `0x360fc`: `insertintoemailmruxml`

## pseudocode

```c

```

## disassembly

```asm
0x36030  ldarg.0
0x36031  ldfld    class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Utility.MruEntityList::_userEntityUISettings
0x36036  ldstr    aInsertintoemai// "insertintoemailmruxml"
0x3603b  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x36040  isinst   [mscorlib]System.String
0x36045  stloc.0
0x36046  ldloc.0
0x36047  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3604c  brfalse.s loc_36054
0x3604e  ldstr    aMruMruentities// "<Mru><MruEntities/></Mru>"
0x36053  stloc.0
0x36054  ldloc.0
0x36055  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x3605a  stloc.1
0x3605b  ldloc.1
0x3605c  ldstr    aMru// "/Mru"
0x36061  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x36066  stloc.2
0x36067  ldloc.2
0x36068  brtrue.s loc_3607E
0x3606a  ldloc.1
0x3606b  ldstr    aMru_0// "Mru"
0x36070  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x36075  stloc.2
0x36076  ldloc.1
0x36077  ldloc.2
0x36078  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3607d  pop
0x3607e  ldloc.2
0x3607f  ldstr    aMruentities// "MruEntities"
0x36084  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x36089  stloc.3
0x3608a  ldloc.3
0x3608b  brtrue.s loc_360A1
0x3608d  ldloc.1
0x3608e  ldstr    aMruentities// "MruEntities"
0x36093  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x36098  stloc.3
0x36099  ldloc.2
0x3609a  ldloc.3
0x3609b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x360a0  pop
0x360a1  ldloc.3
0x360a2  callvirt instance void [System.Xml]System.Xml.XmlNode::RemoveAll()
0x360a7  ldarg.0
0x360a8  ldfld    class [System]System.Collections.Generic.SortedList`2<valuetype [mscorlib]System.DateTime, class Microsoft.Crm.Application.Utility.MruEntity> Microsoft.Crm.Application.Utility.MruEntityList::_items
0x360ad  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [System]System.Collections.Generic.SortedList`2<valuetype [mscorlib]System.DateTime, class Microsoft.Crm.Application.Utility.MruEntity>::get_Values()
0x360b2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Application.Utility.MruEntity>::GetEnumerator()
0x360b7  stloc.s  4
0x360b9  br.s     loc_360DF
0x360bb  ldloc.s  4
0x360bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Utility.MruEntity>::get_Current()
0x360c2  ldloc.1
0x360c3  ldstr    aMruentity// "MruEntity"
0x360c8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x360cd  stloc.s  5
0x360cf  ldloc.s  5
0x360d1  callvirt instance void Microsoft.Crm.Application.Utility.MruEntity::PopulateXmlElement(class [System.Xml]System.Xml.XmlElement entityElement)
0x360d6  ldloc.3
0x360d7  ldloc.s  5
0x360d9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x360de  pop
0x360df  ldloc.s  4
0x360e1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x360e6  brtrue.s loc_360BB
0x360e8  leave.s  loc_360F6
0x360ea  ldloc.s  4
0x360ec  brfalse.s loc_360F5
0x360ee  ldloc.s  4
0x360f0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x360f5  endfinally
0x360f6  ldarg.0
0x360f7  ldfld    class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Utility.MruEntityList::_userEntityUISettings
0x360fc  ldstr    aInsertintoemai// "insertintoemailmruxml"
0x36101  ldloc.1
0x36102  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x36107  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x3610c  ret
```
