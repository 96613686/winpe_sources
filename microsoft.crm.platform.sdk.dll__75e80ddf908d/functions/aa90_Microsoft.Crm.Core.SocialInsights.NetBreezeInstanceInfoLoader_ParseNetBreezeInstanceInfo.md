# Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfoLoader::ParseNetBreezeInstanceInfo

- ea: `0xaa90`
- end: `0xab6d`
- name: `Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfoLoader::ParseNetBreezeInstanceInfo`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xaa90`
- `0xad50`

## string_xrefs

- `0xaab9`: `ServiceParameters`
- `0xaace`: `ServiceParameter`
- `0xaa90`: `http://schemas.microsoft.com/online/serviceextensions/2009/08/ExtensibilitySchema.xsd`

## pseudocode

```c

```

## disassembly

```asm
0xaa90  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/online/ser"...
0xaa95  call     class [System.Xml.Linq]System.Xml.Linq.XNamespace [System.Xml.Linq]System.Xml.Linq.XNamespace::op_Implicit(string)
0xaa9a  stloc.0
0xaa9b  ldarg.0
0xaa9c  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.ServiceInfoValue [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueServiceInfo::get_Info()
0xaaa1  callvirt instance class [System.Xml]System.Xml.XmlElement[] [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.ServiceInfoValue::get_Any()
0xaaa6  ldc.i4.0
0xaaa7  ldelem.ref
0xaaa8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xaaad  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Parse(string)
0xaab2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xaab7  stloc.1
0xaab8  ldloc.0
0xaab9  ldstr    aServiceparamet// "ServiceParameters"
0xaabe  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XNamespace::op_Addition(class [System.Xml.Linq]System.Xml.Linq.XNamespace, string)
0xaac3  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0xaac8  stloc.2
0xaac9  ldloc.2
0xaaca  brfalse.s loc_AB3F
0xaacc  ldloc.2
0xaacd  ldloc.0
0xaace  ldstr    aServiceparamet_0// "ServiceParameter"
0xaad3  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XNamespace::op_Addition(class [System.Xml.Linq]System.Xml.Linq.XNamespace, string)
0xaad8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0xaadd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0xaae2  stloc.3
0xaae3  br.s     loc_AB2B
0xaae5  ldloc.3
0xaae6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0xaaeb  stloc.s  4
0xaaed  ldloc.1
0xaaee  ldloc.s  4
0xaaf0  ldloc.0
0xaaf1  ldstr    aName// "Name"
0xaaf6  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XNamespace::op_Addition(class [System.Xml.Linq]System.Xml.Linq.XNamespace, string)
0xaafb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0xab00  call     T0x2B000028
0xab05  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0xab0a  ldloc.s  4
0xab0c  ldloc.0
0xab0d  ldstr    aValue_0// "Value"
0xab12  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XNamespace::op_Addition(class [System.Xml.Linq]System.Xml.Linq.XNamespace, string)
0xab17  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0xab1c  call     T0x2B000028
0xab21  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0xab26  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xab2b  ldloc.3
0xab2c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xab31  brtrue.s loc_AAE5
0xab33  leave.s  loc_AB3F
0xab35  ldloc.3
0xab36  brfalse.s loc_AB3E
0xab38  ldloc.3
0xab39  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xab3e  endfinally
0xab3f  ldloc.1
0xab40  ldstr    aSolutionid// "SolutionId"
0xab45  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0xab4a  brfalse.s loc_AB59
0xab4c  ldloc.1
0xab4d  ldstr    aSolutionname// "SolutionName"
0xab52  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0xab57  brtrue.s loc_AB5B
0xab59  ldnull
0xab5a  ret
0xab5b  ldarg.0
0xab5c  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.ServiceInfoValue [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueServiceInfo::get_Info()
0xab61  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.ServiceInfoValue::get_ServiceInstance()
0xab66  ldloc.1
0xab67  newobj   instance void Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo::.ctor(string serviceInstanceName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> parameters)
0xab6c  ret
```
