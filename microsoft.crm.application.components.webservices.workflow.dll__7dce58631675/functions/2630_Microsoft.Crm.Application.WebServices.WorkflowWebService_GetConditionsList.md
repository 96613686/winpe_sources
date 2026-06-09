# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetConditionsList

- ea: `0x2630`
- end: `0x26f6`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetConditionsList`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2500`

## callees

- `0x25f0`
- `0x2630`

## string_xrefs

- `0x26c5`: `Xml format not supported`

## pseudocode

```c

```

## disassembly

```asm
0x2630  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2635  stloc.0
0x2636  ldarg.1
0x2637  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x263c  pop
0x263d  ldarg.1
0x263e  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_Name()
0x2643  ldstr    aCondition// "condition"
0x2648  ldc.i4.5
0x2649  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x264e  ldstr    aInvalidInput// "Invalid input"
0x2653  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2658  ldarg.1
0x2659  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x265e  pop
0x265f  ldarg.1
0x2660  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x2665  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x266a  brtrue.s loc_26D0
0x266c  ldarg.1
0x266d  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x2672  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x2677  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x267c  ldstr    aSlugbody// "slugbody"
0x2681  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x2686  stloc.1
0x2687  ldloc.1
0x2688  brfalse.s loc_26C5
0x268a  ldloc.1
0x268b  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x2690  stloc.2
0x2691  ldloc.2
0x2692  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x2697  pop
0x2698  ldloc.2
0x2699  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x269e  pop
0x269f  ldsfld   string [mscorlib]System.String::Empty
0x26a4  stloc.3
0x26a5  br.s     loc_26B4
0x26a7  ldloc.3
0x26a8  ldloc.2
0x26a9  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x26ae  call     string [mscorlib]System.String::Concat(string, string)
0x26b3  stloc.3
0x26b4  ldloc.2
0x26b5  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext()
0x26ba  brtrue.s loc_26A7
0x26bc  ldloc.0
0x26bd  ldloc.3
0x26be  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x26c3  br.s     loc_26E2
0x26c5  ldstr    aXmlFormatNotSu// "Xml format not supported"
0x26ca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x26cf  throw
0x26d0  ldloc.0
0x26d1  ldarg.0
0x26d2  ldarg.1
0x26d3  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x26d8  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::GetPrimitiveNodeAsString(string value)
0x26dd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x26e2  ldarg.1
0x26e3  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToParent()
0x26e8  pop
0x26e9  ldarg.1
0x26ea  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext()
0x26ef  brtrue   loc_263D
0x26f4  ldloc.0
0x26f5  ret
```
