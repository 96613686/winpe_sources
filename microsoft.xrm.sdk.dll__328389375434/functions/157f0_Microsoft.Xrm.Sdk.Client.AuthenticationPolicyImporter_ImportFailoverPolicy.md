# Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportFailoverPolicy

- ea: `0x157f0`
- end: `0x15889`
- name: `Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportFailoverPolicy`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x15720`
- `0x15890`

## callees

- `0x157f0`
- `0x15a90`
- `0x15d00`

## string_xrefs

- `0x157fb`: `http://schemas.microsoft.com/xrm/2012/Contracts/Services`
- `0x15857`: `http://schemas.microsoft.com/xrm/2012/Contracts/Services`

## pseudocode

```c

```

## disassembly

```asm
0x157f0  ldarg.1
0x157f1  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.PolicyAssertionCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::GetBindingAssertions()
0x157f6  ldstr    aFailoverpolicy// "FailoverPolicy"
0x157fb  ldstr    aHttpSchemasMic_16// "http://schemas.microsoft.com/xrm/2012/C"...
0x15800  callvirt instance class [System.Xml]System.Xml.XmlElement [System.ServiceModel]System.ServiceModel.Description.PolicyAssertionCollection::Find(string, string)
0x15805  stloc.0
0x15806  ldloc.0
0x15807  brfalse.s loc_15887
0x15809  ldc.i4.1
0x1580a  ldarg.1
0x1580b  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::get_BindingElements()
0x15810  callvirt T0x2B00005D
0x15815  stloc.1
0x15816  ldloc.1
0x15817  brtrue.s loc_1582C
0x15819  newobj   instance void Microsoft.Xrm.Sdk.Client.FailoverPolicy::.ctor()
0x1581e  stloc.1
0x1581f  ldarg.1
0x15820  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::get_BindingElements()
0x15825  ldc.i4.0
0x15826  ldloc.1
0x15827  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Channels.BindingElement>::Insert(int32, var<u1>)
0x1582c  ldarg.1
0x1582d  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.PolicyAssertionCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::GetBindingAssertions()
0x15832  ldloc.0
0x15833  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement>::Remove(var<u1>)
0x15838  pop
0x15839  brfalse.s loc_15885
0x1583b  ldloc.0
0x1583c  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x15841  stloc.2
0x15842  ldloc.2
0x15843  brfalse.s loc_15885
0x15845  ldloc.2
0x15846  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XPath.XPathNavigator::get_NameTable()
0x1584b  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x15850  stloc.3
0x15851  ldloc.3
0x15852  ldstr    aMsXrm// "ms-xrm"
0x15857  ldstr    aHttpSchemasMic_16// "http://schemas.microsoft.com/xrm/2012/C"...
0x1585c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x15861  ldloc.1
0x15862  ldloc.2
0x15863  ldloc.3
0x15864  ldstr    aMsXrmFailovera// "ms-xrm:FailoverAvailable"
0x15869  ldstr    aFailoveravaila// "FailoverAvailable"
0x1586e  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x15873  ldloc.1
0x15874  ldloc.2
0x15875  ldloc.3
0x15876  ldstr    aMsXrmEndpointe// "ms-xrm:EndpointEnabled"
0x1587b  ldstr    aEndpointenable// "EndpointEnabled"
0x15880  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x15885  ldc.i4.1
0x15886  ret
0x15887  ldc.i4.0
0x15888  ret
```
