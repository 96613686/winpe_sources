# Microsoft.Crm.Application.Ribbon.RibbonXml::ReplaceDynamicMenuLayoutXml

- ea: `0x54560`
- end: `0x5468c`
- name: `Microsoft.Crm.Application.Ribbon.RibbonXml::ReplaceDynamicMenuLayoutXml`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x540d0`

## callees

- `0xc30`
- `0x4f6e0`
- `0x4fcb0`
- `0x4fcc0`
- `0x4fcd0`
- `0x54560`

## string_xrefs

- `0x54591`: `PopulateQueryCommand`
- `0x545e7`: `PopulateQueryCommand`

## pseudocode

```c

```

## disassembly

```asm
0x54560  ldarg.0
0x54561  ldstr    aFlyoutanchorPo// "//FlyoutAnchor[@PopulateDynamically = '"...
0x54566  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x5456b  stloc.0
0x5456c  ldloc.0
0x5456d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x54572  stloc.1
0x54573  br       loc_54660
0x54578  ldloc.1
0x54579  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5457e  castclass [System.Xml]System.Xml.XmlElement
0x54583  stloc.2
0x54584  ldloc.2
0x54585  ldstr    aId_0// "Id"
0x5458a  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x5458f  stloc.3
0x54590  ldloc.2
0x54591  ldstr    aPopulatequeryc// "PopulateQueryCommand"
0x54596  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x5459b  ldloc.3
0x5459c  ldarg.1
0x5459d  ldarg.2
0x5459e  ldarg.s  4
0x545a0  ldarg.3
0x545a1  ldarg.s  5
0x545a3  call     class Microsoft.Crm.Application.Ribbon.IDynamicMenuBuilder Microsoft.Crm.Application.Ribbon.DynamicMenuBuilderFactory::GetDynamicMenuBuilder(string commandId, string idPrefix, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, int32 languageCode, class Microsoft.Crm.Application.Ribbon.RibbonPageContext pageContext, class Microsoft.Crm.Application.Ribbon.IMenuBuilderFactory menuBuilderFactory, bool replaceLocalStrings)
0x545a8  stloc.s  4
0x545aa  ldloc.s  4
0x545ac  brfalse  loc_5464C
0x545b1  ldstr    aDynamicmenubui// "DynamicMenuBuilder found for dynamic me"...
0x545b6  ldc.i4.1
0x545b7  newarr   [mscorlib]System.Object
0x545bc  dup
0x545bd  ldc.i4.0
0x545be  ldloc.3
0x545bf  stelem.ref
0x545c0  call     void Microsoft.Crm.Util::TraceVerbose(string message, object[] args)
0x545c5  ldloc.2
0x545c6  ldloc.s  4
0x545c8  callvirt instance string Microsoft.Crm.Application.Ribbon.IDynamicMenuBuilder::get_LayoutXml()
0x545cd  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x545d2  ldloc.s  4
0x545d4  callvirt instance bool Microsoft.Crm.Application.Ribbon.IDynamicMenuBuilder::get_RemoveRootNodePopulateAttributes()
0x545d9  brfalse.s loc_545FC
0x545db  ldloc.2
0x545dc  ldstr    aPopulatedynami// "PopulateDynamically"
0x545e1  callvirt instance void [System.Xml]System.Xml.XmlElement::RemoveAttribute(string)
0x545e6  ldloc.2
0x545e7  ldstr    aPopulatequeryc// "PopulateQueryCommand"
0x545ec  callvirt instance void [System.Xml]System.Xml.XmlElement::RemoveAttribute(string)
0x545f1  ldloc.2
0x545f2  ldstr    aPopulateonlyon// "PopulateOnlyOnce"
0x545f7  callvirt instance void [System.Xml]System.Xml.XmlElement::RemoveAttribute(string)
0x545fc  ldloc.s  4
0x545fe  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.IDynamicMenuBuilder::get_RootNodeAttributes()
0x54603  stloc.s  5
0x54605  ldloc.s  5
0x54607  brfalse.s loc_54660
0x54609  ldloc.s  5
0x5460b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0x54610  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, string>::GetEnumerator()
0x54615  stloc.s  6
0x54617  br.s     loc_54633
0x54619  ldloca.s 6
0x5461b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::get_Current()
0x54620  stloc.s  7
0x54622  ldloc.2
0x54623  ldloc.s  7
0x54625  ldloc.s  5
0x54627  ldloc.s  7
0x54629  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x5462e  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x54633  ldloca.s 6
0x54635  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::MoveNext()
0x5463a  brtrue.s loc_54619
0x5463c  leave.s  loc_54660
0x5463e  ldloca.s 6
0x54640  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>
0x54646  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5464b  endfinally
0x5464c  ldstr    aNoDynamicmenub// "No DynamicMenuBuilder found for dynamic"...
0x54651  ldc.i4.1
0x54652  newarr   [mscorlib]System.Object
0x54657  dup
0x54658  ldc.i4.0
0x54659  ldloc.3
0x5465a  stelem.ref
0x5465b  call     void Microsoft.Crm.Util::TraceVerbose(string message, object[] args)
0x54660  ldloc.1
0x54661  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x54666  brtrue   loc_54578
0x5466b  leave.s  loc_5468B
0x5466d  ldloc.1
0x5466e  isinst   [mscorlib]System.IDisposable
0x54673  stloc.s  8
0x54675  ldloc.s  8
0x54677  brfalse.s loc_54680
0x54679  ldloc.s  8
0x5467b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54680  endfinally
0x54681  ldloc.0
0x54682  brfalse.s loc_5468A
0x54684  ldloc.0
0x54685  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5468a  endfinally
0x5468b  ret
```
