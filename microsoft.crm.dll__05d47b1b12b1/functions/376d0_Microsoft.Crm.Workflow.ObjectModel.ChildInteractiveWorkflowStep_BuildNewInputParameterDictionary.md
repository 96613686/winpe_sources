# Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::BuildNewInputParameterDictionary

- ea: `0x376d0`
- end: `0x3792d`
- name: `Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::BuildNewInputParameterDictionary`
- size: `605`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callees

- `0x30900`
- `0x32ec0`
- `0x35f70`
- `0x35fb0`
- `0x36000`
- `0x36010`
- `0x36030`
- `0x36070`
- `0x36080`
- `0x360b0`
- `0x360d0`
- `0x360e0`
- `0x36120`
- `0x361b0`
- `0x376d0`
- `0x37930`
- `0x390a0`
- `0x39120`
- `0x39270`
- `0x39290`
- `0x39990`
- `0x399e0`
- `0x39a00`
- `0x39a90`
- `0x39ab0`
- `0x39b00`
- `0x3a040`

## string_xrefs

- `0x3774b`: `Invalid input parameters XML`
- `0x377e6`: `Invalid input parameters XML. Missing value`

## pseudocode

```c

```

## disassembly

```asm
0x376d0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor()
0x376d5  stloc.0
0x376d6  ldarg.1
0x376d7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x376dc  brtrue   loc_3792B
0x376e1  ldarg.1
0x376e2  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x376e7  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x376ec  ldstr    aParametersPara// "//parameters/parameter"
0x376f1  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x376f6  stloc.1
0x376f7  br       loc_37920
0x376fc  ldloc.1
0x376fd  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x37702  dup
0x37703  ldstr    aName_0// "name"
0x37708  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3770d  stloc.2
0x3770e  dup
0x3770f  ldstr    aDisplayname// "displayname"
0x37714  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x37719  stloc.3
0x3771a  dup
0x3771b  ldstr    aType_0// "type"
0x37720  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x37725  stloc.s  4
0x37727  dup
0x37728  ldstr    aValue// "value"
0x3772d  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x37732  stloc.s  5
0x37734  ldstr    aIdentifierdefi// "IdentifierDefinition"
0x37739  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3773e  stloc.s  6
0x37740  ldloc.2
0x37741  brfalse.s loc_3774A
0x37743  ldloc.s  4
0x37745  ldnull
0x37746  cgt.un
0x37748  br.s     loc_3774B
0x3774a  ldc.i4.0
0x3774b  ldstr    aInvalidInputPa// "Invalid input parameters XML"
0x37750  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x37755  ldloc.s  4
0x37757  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3775c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x37761  stloc.s  7
0x37763  ldnull
0x37764  stloc.s  8
0x37766  ldloca.s 9
0x37768  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>
0x3776e  ldloc.s  6
0x37770  brfalse.s loc_377E1
0x37772  ldloca.s 9
0x37774  ldtoken  Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x37779  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3777e  call     class [System]System.ComponentModel.TypeConverter [System]System.ComponentModel.TypeDescriptor::GetConverter(class [mscorlib]System.Type)
0x37783  ldloc.s  6
0x37785  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3778a  callvirt instance object [System]System.ComponentModel.TypeConverter::ConvertFromInvariantString(string)
0x3778f  unbox.any Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x37794  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::.ctor(var<u1>)
0x37799  ldloca.s 9
0x3779b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x377a0  stloc.s  0xB
0x377a2  ldloca.s 0xB
0x377a4  call     instance void Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::ThrowIfInvalid()
0x377a9  ldloca.s 9
0x377ab  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x377b0  stloc.s  0xB
0x377b2  ldloca.s 0xB
0x377b4  call     instance class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::GetClrType()
0x377b9  stloc.s  7
0x377bb  ldloca.s 9
0x377bd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x377c2  stloc.s  0xB
0x377c4  ldloca.s 0xB
0x377c6  call     instance bool Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_HasValue()
0x377cb  brfalse.s loc_377FB
0x377cd  ldloca.s 9
0x377cf  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x377d4  stloc.s  0xB
0x377d6  ldloca.s 0xB
0x377d8  call     instance object Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_Value()
0x377dd  stloc.s  8
0x377df  br.s     loc_377FB
0x377e1  ldloc.s  5
0x377e3  ldnull
0x377e4  cgt.un
0x377e6  ldstr    aInvalidInputPa_0// "Invalid input parameters XML. Missing v"...
0x377eb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x377f0  ldloc.s  5
0x377f2  ldloc.s  7
0x377f4  callvirt instance object [System.Xml]System.Xml.XPath.XPathItem::ValueAs(class [mscorlib]System.Type)
0x377f9  stloc.s  8
0x377fb  newobj   instance void Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo::.ctor()
0x37800  stloc.s  0xA
0x37802  ldloc.s  0xA
0x37804  ldloc.3
0x37805  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3780a  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Name(string value)
0x3780f  ldloc.s  0xA
0x37811  ldloc.s  7
0x37813  callvirt instance string [mscorlib]System.Type::get_FullName()
0x37818  call     class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.InteractiveWorkflowTypeHelper::GetCrmTypeFromDotNetType(string dotNetTypeFullName)
0x3781d  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Type(class [mscorlib]System.Type value)
0x37822  ldloc.s  0xA
0x37824  ldloc.s  0xA
0x37826  ldloc.s  8
0x37828  dup
0x37829  stloc.s  0xC
0x3782b  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Value(object value)
0x37830  ldloc.s  0xC
0x37832  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_DefaultValue(object value)
0x37837  ldloc.s  0xA
0x37839  ldloc.2
0x3783a  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3783f  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_DependencyPropertyName(string value)
0x37844  ldloc.s  0xA
0x37846  ldc.i4.1
0x37847  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Required(bool value)
0x3784c  ldloca.s 9
0x3784e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_HasValue()
0x37853  brfalse  loc_378FD
0x37858  ldloc.s  0xA
0x3785a  ldloca.s 9
0x3785c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x37861  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::.ctor(var<u1>)
0x37866  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_IdentifierDefinition(valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition> value)
0x3786b  ldloc.s  0xA
0x3786d  ldloca.s 9
0x3786f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x37874  stloc.s  0xB
0x37876  ldloca.s 0xB
0x37878  call     instance valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::GetWorkflowDataType()
0x3787d  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_WorkflowAttributeType(valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType value)
0x37882  ldloc.s  0xA
0x37884  callvirt instance valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_WorkflowAttributeType()
0x37889  ldc.i4.6
0x3788a  bne.un   loc_37910
0x3788f  ldarg.0
0x37890  call     instance class Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x37895  callvirt instance class Microsoft.Crm.Workflow.ObjectModel.IMetadataProvider Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_MetadataProvider()
0x3789a  ldloca.s 9
0x3789c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x378a1  stloc.s  0xB
0x378a3  ldloca.s 0xB
0x378a5  call     instance valuetype Microsoft.Crm.Workflow.ObjectModel.MetadataSource Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_MetadataSource()
0x378aa  stloc.s  0xF
0x378ac  ldloca.s 0xF
0x378ae  call     instance string Microsoft.Crm.Workflow.ObjectModel.MetadataSource::get_EntityName()
0x378b3  ldloca.s 9
0x378b5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x378ba  stloc.s  0xB
0x378bc  ldloca.s 0xB
0x378be  call     instance valuetype Microsoft.Crm.Workflow.ObjectModel.MetadataSource Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_MetadataSource()
0x378c3  stloc.s  0xF
0x378c5  ldloca.s 0xF
0x378c7  call     instance string Microsoft.Crm.Workflow.ObjectModel.MetadataSource::get_AttributeName()
0x378cc  callvirt instance string[] Microsoft.Crm.Workflow.ObjectModel.IMetadataProvider::GetEntitiesReferencedByLookup(string entityName, string attributeName)
0x378d1  stloc.s  0xD
0x378d3  ldc.i4.0
0x378d4  stloc.s  0xE
0x378d6  br.s     loc_378F3
0x378d8  ldloc.s  0xD
0x378da  ldloc.s  0xE
0x378dc  ldelem.ref
0x378dd  stloc.s  0x10
0x378df  ldloc.s  0xA
0x378e1  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_EntityNames()
0x378e6  ldloc.s  0x10
0x378e8  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x378ed  ldloc.s  0xE
0x378ef  ldc.i4.1
0x378f0  add
0x378f1  stloc.s  0xE
0x378f3  ldloc.s  0xE
0x378f5  ldloc.s  0xD
0x378f7  ldlen
0x378f8  conv.i4
0x378f9  blt.s    loc_378D8
0x378fb  br.s     loc_37910
0x378fd  ldloc.s  0xA
0x378ff  ldloc.s  0xA
0x37901  callvirt instance class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x37906  call     valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType Microsoft.Crm.Workflow.ObjectModel.InteractiveWorkflowTypeHelper::GetWorkflowType(class [mscorlib]System.Type crmType)
0x3790b  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_WorkflowAttributeType(valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType value)
0x37910  ldloc.0
0x37911  ldloc.s  0xA
0x37913  ldarg.0
0x37914  ldloc.s  0xA
0x37916  call     instance class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::GetPrimitiveExpression(class Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo parameter)
0x3791b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>, !!T0)
0x37920  ldloc.1
0x37921  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x37926  brtrue   loc_376FC
0x3792b  ldloc.0
0x3792c  ret
```
