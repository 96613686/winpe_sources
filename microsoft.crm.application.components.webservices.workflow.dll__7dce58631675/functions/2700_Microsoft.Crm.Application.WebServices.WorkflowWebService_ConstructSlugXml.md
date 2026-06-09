# Microsoft.Crm.Application.WebServices.WorkflowWebService::ConstructSlugXml

- ea: `0x2700`
- end: `0x27b8`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::ConstructSlugXml`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2500`

## callees

- `0x25c0`
- `0x2700`

## string_xrefs

- `0x2792`: `Xml format not supported`
- `0x2716`: `Error in XML structure (Number of conditions not supported by XML)`

## pseudocode

```c

```

## disassembly

```asm
0x2700  ldarg.2
0x2701  ldloca.s 0
0x2703  call     class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.UIWorkflowQueryAdvancedModeUtility::GetVariableIndexListFromFetch(string, string[]&)
0x2708  stloc.1
0x2709  ldarg.3
0x270a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x270f  ldloc.0
0x2710  ldlen
0x2711  conv.i4
0x2712  ldc.i4.1
0x2713  sub
0x2714  ceq
0x2716  ldstr    aErrorInXmlStru// "Error in XML structure (Number of condi"...
0x271b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2720  ldarg.0
0x2721  ldarg.1
0x2722  ldloc.0
0x2723  ldc.i4.0
0x2724  ldelem.ref
0x2725  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::WritePrimitiveSlugNode(class [System.Xml]System.Xml.XmlWriter xmlWriter, string value)
0x272a  ldc.i4.1
0x272b  stloc.2
0x272c  br.s     loc_27AB
0x272e  ldstr    aSlugbody_0// "<slugbody>"
0x2733  ldarg.3
0x2734  ldloc.1
0x2735  ldloc.2
0x2736  ldc.i4.1
0x2737  sub
0x2738  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::get_Item(!!T0)
0x273d  ldc.i4.1
0x273e  sub
0x273f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x2744  ldstr    aSlugbody_1// "</slugbody>"
0x2749  call     string [mscorlib]System.String::Concat(string, string, string)
0x274e  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x2753  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x2758  ldstr    aSlugbody// "slugbody"
0x275d  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x2762  stloc.3
0x2763  ldloc.3
0x2764  brfalse.s loc_2792
0x2766  ldloc.3
0x2767  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x276c  stloc.s  4
0x276e  ldloc.s  4
0x2770  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x2775  pop
0x2776  ldloc.s  4
0x2778  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x277d  pop
0x277e  ldarg.1
0x277f  ldloc.s  4
0x2781  ldc.i4.1
0x2782  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteNode(class [System.Xml]System.Xml.XPath.XPathNavigator, bool)
0x2787  ldloc.s  4
0x2789  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext()
0x278e  brtrue.s loc_277E
0x2790  br.s     loc_279D
0x2792  ldstr    aXmlFormatNotSu// "Xml format not supported"
0x2797  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x279c  throw
0x279d  ldarg.0
0x279e  ldarg.1
0x279f  ldloc.0
0x27a0  ldloc.2
0x27a1  ldelem.ref
0x27a2  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::WritePrimitiveSlugNode(class [System.Xml]System.Xml.XmlWriter xmlWriter, string value)
0x27a7  ldloc.2
0x27a8  ldc.i4.1
0x27a9  add
0x27aa  stloc.2
0x27ab  ldloc.2
0x27ac  ldarg.3
0x27ad  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x27b2  ble      loc_272E
0x27b7  ret
```
