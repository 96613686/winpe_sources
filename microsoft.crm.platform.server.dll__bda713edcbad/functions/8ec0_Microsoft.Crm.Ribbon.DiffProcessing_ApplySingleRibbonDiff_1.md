# Microsoft.Crm.Ribbon.DiffProcessing::ApplySingleRibbonDiff_1

- ea: `0x8ec0`
- end: `0x9094`
- name: `Microsoft.Crm.Ribbon.DiffProcessing::ApplySingleRibbonDiff_1`
- size: `468`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8e80`
- `0x8ea0`

## callees

- `0x8ec0`
- `0x90a0`
- `0x9140`
- `0x9e80`

## string_xrefs

- `0x8edc`: `ApplySingleRibbonDiff: skipped. Custom action XML is null.`
- `0x8f98`: `ApplySingleRibbonDiff: skipped. Custom action XML is does not contain a required location property.`

## pseudocode

```c

```

## disassembly

```asm
0x8ec0  ldarg.2
0x8ec1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8ec6  brfalse.s loc_8EED
0x8ec8  ldarg.s  6
0x8eca  brtrue.s loc_8ED3
0x8ecc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8ed1  br.s     loc_8EDA
0x8ed3  ldarg.s  6
0x8ed5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x8eda  ldc.i4.s 0x14
0x8edc  ldstr    aApplysinglerib// "ApplySingleRibbonDiff: skipped. Custom "...
0x8ee1  ldc.i4.0
0x8ee2  newarr   [mscorlib]System.Object
0x8ee7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8eec  ret
0x8eed  ldarg.3
0x8eee  ldc.i4.2
0x8eef  bne.un.s loc_8EF9
0x8ef1  ldarg.1
0x8ef2  ldarg.2
0x8ef3  call     void Microsoft.Crm.Ribbon.DiffProcessing::ApplyTemplateDiff(class [System.Xml]System.Xml.XmlDocument layoutXml, string rdxValue)
0x8ef8  ret
0x8ef9  ldarg.2
0x8efa  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Parse(string)
0x8eff  stloc.0
0x8f00  ldloc.0
0x8f01  brtrue.s loc_8F04
0x8f03  ret
0x8f04  ldc.i4.0
0x8f05  stloc.1
0x8f06  ldloc.0
0x8f07  ldstr    aHidecustomacti// "HideCustomAction"
0x8f0c  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x8f11  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XElement::DescendantsAndSelf(class [System.Xml.Linq]System.Xml.Linq.XName)
0x8f16  call     T0x2B00000A
0x8f1b  stloc.2
0x8f1c  ldloc.2
0x8f1d  brfalse.s loc_8F23
0x8f1f  ldc.i4.1
0x8f20  stloc.1
0x8f21  br.s     loc_8F39
0x8f23  ldloc.0
0x8f24  ldstr    aCustomaction// "CustomAction"
0x8f29  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x8f2e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XElement::DescendantsAndSelf(class [System.Xml.Linq]System.Xml.Linq.XName)
0x8f33  call     T0x2B00000A
0x8f38  stloc.2
0x8f39  ldloc.2
0x8f3a  brtrue.s loc_8F61
0x8f3c  ldarg.s  6
0x8f3e  brtrue.s loc_8F47
0x8f40  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8f45  br.s     loc_8F4E
0x8f47  ldarg.s  6
0x8f49  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x8f4e  ldc.i4.s 0x14
0x8f50  ldstr    aApplysinglerib_0// "ApplySingleRibbonDiff: skipped. CustomA"...
0x8f55  ldc.i4.0
0x8f56  newarr   [mscorlib]System.Object
0x8f5b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8f60  ret
0x8f61  ldloc.2
0x8f62  ldstr    aLocation// "Location"
0x8f67  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x8f6c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XAttribute> [System.Xml.Linq]System.Xml.Linq.XElement::Attributes(class [System.Xml.Linq]System.Xml.Linq.XName)
0x8f71  call     T0x2B00000B
0x8f76  call     string [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x8f7b  stloc.3
0x8f7c  ldloc.3
0x8f7d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8f82  brfalse.s loc_8FA9
0x8f84  ldarg.s  6
0x8f86  brtrue.s loc_8F8F
0x8f88  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8f8d  br.s     loc_8F96
0x8f8f  ldarg.s  6
0x8f91  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x8f96  ldc.i4.s 0x14
0x8f98  ldstr    aApplysinglerib_1// "ApplySingleRibbonDiff: skipped. Custom "...
0x8f9d  ldc.i4.0
0x8f9e  newarr   [mscorlib]System.Object
0x8fa3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8fa8  ret
0x8fa9  ldloc.1
0x8faa  ldc.i4.1
0x8fab  beq.s    loc_8FDD
0x8fad  ldloc.3
0x8fae  ldstr    aChildren// "._children"
0x8fb3  ldc.i4.4
0x8fb4  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x8fb9  brtrue.s loc_8FBE
0x8fbb  ldc.i4.3
0x8fbc  br.s     loc_8FBF
0x8fbe  ldc.i4.2
0x8fbf  stloc.1
0x8fc0  ldloc.1
0x8fc1  ldc.i4.2
0x8fc2  bne.un.s loc_8FDD
0x8fc4  ldloc.3
0x8fc5  ldc.i4.0
0x8fc6  ldloc.3
0x8fc7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8fcc  ldstr    aChildren// "._children"
0x8fd1  call     instance int32 [mscorlib]System.String::get_Length()
0x8fd6  sub
0x8fd7  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x8fdc  stloc.3
0x8fdd  ldarg.0
0x8fde  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8fe3  brtrue.s loc_9010
0x8fe5  ldc.i4.3
0x8fe6  newarr   [mscorlib]System.String
0x8feb  dup
0x8fec  ldc.i4.0
0x8fed  ldloc.3
0x8fee  stelem.ref
0x8fef  dup
0x8ff0  ldc.i4.1
0x8ff1  ldloc.3
0x8ff2  ldarg.0
0x8ff3  ldarg.s  4
0x8ff5  ldarg.s  5
0x8ff7  call     string Microsoft.Crm.Ribbon.RibbonPlatformXml::MarkEntityTabId(string originalTabId, string entityLogicalName, valuetype [Microsoft.Crm]Microsoft.Crm.RibbonRuleRelationshipType relationshipType, string entityContext)
0x8ffc  stelem.ref
0x8ffd  dup
0x8ffe  ldc.i4.2
0x8fff  ldloc.3
0x9000  ldarg.0
0x9001  ldstr    aEntitylogicaln// "{!EntityLogicalName}"
0x9006  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x900b  stelem.ref
0x900c  stloc.s  4
0x900e  br.s     loc_901C
0x9010  ldc.i4.1
0x9011  newarr   [mscorlib]System.String
0x9016  dup
0x9017  ldc.i4.0
0x9018  ldloc.3
0x9019  stelem.ref
0x901a  stloc.s  4
0x901c  ldnull
0x901d  stloc.s  5
0x901f  ldloc.s  4
0x9021  stloc.s  6
0x9023  ldc.i4.0
0x9024  stloc.s  7
0x9026  br.s     loc_9052
0x9028  ldloc.s  6
0x902a  ldloc.s  7
0x902c  ldelem.ref
0x902d  stloc.s  8
0x902f  ldarg.1
0x9030  ldstr    aId// "//*[@Id=\""
0x9035  ldloc.s  8
0x9037  ldstr    asc_C56F8// "\"]"
0x903c  call     string [mscorlib]System.String::Concat(string, string, string)
0x9041  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x9046  stloc.s  5
0x9048  ldloc.s  5
0x904a  brtrue.s loc_905A
0x904c  ldloc.s  7
0x904e  ldc.i4.1
0x904f  add
0x9050  stloc.s  7
0x9052  ldloc.s  7
0x9054  ldloc.s  6
0x9056  ldlen
0x9057  conv.i4
0x9058  blt.s    loc_9028
0x905a  ldloc.s  5
0x905c  brtrue.s loc_9083
0x905e  ldarg.s  6
0x9060  brtrue.s loc_9069
0x9062  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9067  br.s     loc_9070
0x9069  ldarg.s  6
0x906b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x9070  ldc.i4.s 0x14
0x9072  ldstr    aApplysinglerib_2// "ApplySingleRibbonDiff: skipped. Locatio"...
0x9077  ldc.i4.0
0x9078  newarr   [mscorlib]System.Object
0x907d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9082  ret
0x9083  ldloc.1
0x9084  ldloc.s  5
0x9086  ldloc.0
0x9087  ldarg.0
0x9088  ldarg.s  4
0x908a  ldarg.s  5
0x908c  ldarg.s  6
0x908e  call     void Microsoft.Crm.Ribbon.DiffProcessing::ExecuteCustomAction(valuetype CustomActionType actionType, class [System.Xml]System.Xml.XmlNode locationNode, class [System.Xml.Linq]System.Xml.Linq.XElement rdxDoc, string entityLogicalName, valuetype [Microsoft.Crm]Microsoft.Crm.RibbonRuleRelationshipType relationshipType, string entityContext, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x9093  ret
```
