# Microsoft.Crm.Workflow.Services.InputArgumentValidator::BuildInputParameterDictionary

- ea: `0x14360`
- end: `0x1446c`
- name: `Microsoft.Crm.Workflow.Services.InputArgumentValidator::BuildInputParameterDictionary`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5df0`
- `0x16120`

## callees

- `0x14360`

## string_xrefs

- `0x14415`: `Invalid input parameters XML. Missing identifier definition`

## pseudocode

```c

```

## disassembly

```asm
0x14360  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::.ctor()
0x14365  stloc.0
0x14366  ldarg.0
0x14367  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1436c  brtrue   loc_1446A
0x14371  ldarg.0
0x14372  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x14377  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x1437c  ldstr    aParametersPara// "//parameters/parameter"
0x14381  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x14386  stloc.1
0x14387  br       loc_1445F
0x1438c  ldloc.1
0x1438d  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x14392  dup
0x14393  ldstr    aName// "name"
0x14398  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x1439d  stloc.2
0x1439e  dup
0x1439f  ldstr    aType// "type"
0x143a4  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x143a9  stloc.3
0x143aa  dup
0x143ab  ldstr    aValue// "value"
0x143b0  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x143b5  pop
0x143b6  ldstr    aIdentifierdefi// "IdentifierDefinition"
0x143bb  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x143c0  stloc.s  4
0x143c2  ldloc.3
0x143c3  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x143c8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x143cd  stloc.s  5
0x143cf  ldnull
0x143d0  ldloc.s  5
0x143d2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x143d7  brfalse.s loc_143EF
0x143d9  ldstr    aCouldNotLoadTh// "Could not load the type of the paramete"...
0x143de  ldloc.3
0x143df  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x143e4  call     string [mscorlib]System.String::Concat(string, string)
0x143e9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x143ee  throw
0x143ef  ldloc.s  5
0x143f1  ldtoken  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x143f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x143fb  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x14400  brfalse.s loc_14451
0x14402  ldloc.0
0x14403  ldloc.2
0x14404  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x14409  ldloc.s  5
0x1440b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::Add(var<u1>, !!T0)
0x14410  ldloc.s  4
0x14412  ldnull
0x14413  cgt.un
0x14415  ldstr    aInvalidInputPa// "Invalid input parameters XML. Missing i"...
0x1441a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1441f  ldtoken  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x14424  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14429  call     class [System]System.ComponentModel.TypeConverter [System]System.ComponentModel.TypeDescriptor::GetConverter(class [mscorlib]System.Type)
0x1442e  ldloc.s  4
0x14430  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x14435  callvirt instance object [System]System.ComponentModel.TypeConverter::ConvertFromInvariantString(string)
0x1443a  unbox.any [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x1443f  stloc.s  6
0x14441  ldloca.s 6
0x14443  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::ThrowIfInvalid()
0x14448  ldloca.s 6
0x1444a  call     instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::GetClrType()
0x1444f  stloc.s  5
0x14451  ldloc.0
0x14452  ldloc.2
0x14453  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x14458  ldloc.s  5
0x1445a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::Add(var<u1>, !!T0)
0x1445f  ldloc.1
0x14460  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x14465  brtrue   loc_1438C
0x1446a  ldloc.0
0x1446b  ret
```
