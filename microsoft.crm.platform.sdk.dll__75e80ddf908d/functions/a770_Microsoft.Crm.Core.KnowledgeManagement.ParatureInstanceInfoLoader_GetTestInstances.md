# Microsoft.Crm.Core.KnowledgeManagement.ParatureInstanceInfoLoader::GetTestInstances

- ea: `0xa770`
- end: `0xa86a`
- name: `Microsoft.Crm.Core.KnowledgeManagement.ParatureInstanceInfoLoader::GetTestInstances`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0xa560`

## callees

- `0xa690`
- `0xa770`

## string_xrefs

- `0xa810`: `ServiceParameters`
- `0xa770`: `<ServiceInfo><Value><Info ServiceInstance="ParatureDynamicsCRM/DN001" Version="16.0" xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"><ServiceExtension xmlns="http://schemas.microsoft.com/online/serviceextensions/2009/08/ExtensibilitySchema.xsd"><ServiceParameters CachePolicy="PerCompany"><ServiceParameter><Name>Dynamics Parature_AdminUrl</Name><Value>https://demo.parature.com</Value></ServiceParameter><ServiceParameter><Name>Dynamics Parature_IWUrl</Name><Value>https`
- `0xa7f5`: `ServiceInstance`

## pseudocode

```c

```

## disassembly

```asm
0xa770  ldstr    aServiceinfoVal// "<ServiceInfo><Value><Info ServiceInstan"...
0xa775  stloc.0
0xa776  ldstr    aKminstances// "KMInstances"
0xa77b  ldloc.0
0xa77c  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xa781  callvirt instance string [mscorlib]System.Object::ToString()
0xa786  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Parse(string)
0xa78b  stloc.1
0xa78c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Core.KnowledgeManagement.KMSettings>::.ctor()
0xa791  stloc.2
0xa792  ldloc.1
0xa793  brfalse  loc_A868
0xa798  ldloc.1
0xa799  ldstr    aValue_0// "Value"
0xa79e  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0xa7a3  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0xa7a8  brfalse  loc_A868
0xa7ad  ldloc.1
0xa7ae  ldstr    aValue_0// "Value"
0xa7b3  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0xa7b8  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0xa7bd  ldsfld   class [System.Xml.Linq]System.Xml.Linq.XNamespace Microsoft.Crm.Core.KnowledgeManagement.ParatureInstanceInfoLoader::namespace1
0xa7c2  ldstr    aInfo// "Info"
0xa7c7  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XNamespace::op_Addition(class [System.Xml.Linq]System.Xml.Linq.XNamespace, string)
0xa7cc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0xa7d1  stloc.3
0xa7d2  ldloc.3
0xa7d3  brfalse  loc_A868
0xa7d8  ldloc.3
0xa7d9  call     T0x2B000029
0xa7de  brfalse  loc_A868
0xa7e3  ldloc.3
0xa7e4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0xa7e9  stloc.s  4
0xa7eb  br.s     loc_A851
0xa7ed  ldloc.s  4
0xa7ef  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0xa7f4  dup
0xa7f5  ldstr    aServiceinstanc// "ServiceInstance"
0xa7fa  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::Get(string)
0xa7ff  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0xa804  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0xa809  stloc.s  5
0xa80b  ldsfld   class [System.Xml.Linq]System.Xml.Linq.XNamespace Microsoft.Crm.Core.KnowledgeManagement.ParatureInstanceInfoLoader::namespace2
0xa810  ldstr    aServiceparamet// "ServiceParameters"
0xa815  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XNamespace::op_Addition(class [System.Xml.Linq]System.Xml.Linq.XNamespace, string)
0xa81a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0xa81f  call     T0x2B00002A
0xa824  stloc.s  6
0xa826  ldloc.s  6
0xa828  brfalse.s loc_A851
0xa82a  ldloc.s  6
0xa82c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Count()
0xa831  ldc.i4.0
0xa832  ble.s    loc_A851
0xa834  ldloc.s  6
0xa836  ldc.i4.0
0xa837  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Item(!!T0)
0xa83c  ldloc.s  5
0xa83e  call     class Microsoft.Crm.Core.KnowledgeManagement.KMSettings Microsoft.Crm.Core.KnowledgeManagement.ParatureInstanceInfoLoader::CreateKMSettings(class [System.Xml.Linq]System.Xml.Linq.XElement serviceParameters, string instanceName)
0xa843  stloc.s  7
0xa845  ldloc.s  7
0xa847  brfalse.s loc_A851
0xa849  ldloc.2
0xa84a  ldloc.s  7
0xa84c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Core.KnowledgeManagement.KMSettings>::Add(var<u1>)
0xa851  ldloc.s  4
0xa853  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa858  brtrue.s loc_A7ED
0xa85a  leave.s  loc_A868
0xa85c  ldloc.s  4
0xa85e  brfalse.s loc_A867
0xa860  ldloc.s  4
0xa862  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa867  endfinally
0xa868  ldloc.2
0xa869  ret
```
