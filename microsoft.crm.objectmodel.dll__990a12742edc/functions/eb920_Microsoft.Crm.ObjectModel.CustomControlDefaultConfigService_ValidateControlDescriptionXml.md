# Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService::ValidateControlDescriptionXml

- ea: `0xeb920`
- end: `0xeba6b`
- name: `Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService::ValidateControlDescriptionXml`
- size: `331`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xeb400`
- `0xeb630`

## callees

- `0xeb920`
- `0x1cca70`
- `0x1ccdd0`
- `0x1ccf70`
- `0x1ce420`
- `0x1cef00`

## string_xrefs

- `0xeb92d`: `controldescriptionxml`
- `0xeb962`: `CustomControl import default config encountered entity-level XML configuration is invalid error. The root node should be 'controlDescriptions'. {0}`
- `0xeb980`: `CustomControl import default config encountered entity-level XML configuration is invalid error. The root node should be 'controlDescriptions'. {0}`
- `0xeb9b2`: `CustomControl import default config encountered entity-level XML configuration is invalid error. You can’t use field-level controls. {0}`
- `0xeb9d0`: `CustomControl import default config encountered entity-level XML configuration is invalid error. You can’t use field-level controls. {0}`
- `0xeba1a`: `CustomControl import default config countered entity-level XML configuration is invalid error. {0}`
- `0xeba38`: `CustomControl import default config encountered entity-level XML configuration is invalid error. {0}`

## pseudocode

```c

```

## disassembly

```asm
0xeb920  newobj   instance void Microsoft.Crm.ObjectModel.CustomControlNodeValidationHelper::.ctor()
0xeb925  stloc.0
0xeb926  newobj   instance void Microsoft.Crm.ObjectModel.CustomControlParameterValidationHelper::.ctor()
0xeb92b  stloc.1
0xeb92c  ldarg.1
0xeb92d  ldstr    aControldescrip_2// "controldescriptionxml"
0xeb932  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb937  castclass [mscorlib]System.String
0xeb93c  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xeb941  stloc.2
0xeb942  ldloc.2
0xeb943  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xeb948  callvirt instance string [System.Xml]System.Xml.XmlNode::get_LocalName()
0xeb94d  ldstr    aControldescrip// "controlDescriptions"
0xeb952  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xeb957  brfalse.s loc_EB99F
0xeb959  ldnull
0xeb95a  ldarg.3
0xeb95b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xeb960  ldc.i4.s 0x11
0xeb962  ldstr    aCustomcontrolI_1// "CustomControl import default config enc"...
0xeb967  ldc.i4.1
0xeb968  newarr   [mscorlib]System.Object
0xeb96d  dup
0xeb96e  ldc.i4.0
0xeb96f  ldloc.2
0xeb970  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xeb975  stelem.ref
0xeb976  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xeb97b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeb980  ldstr    aCustomcontrolI_1// "CustomControl import default config enc"...
0xeb985  ldc.i4.1
0xeb986  newarr   [mscorlib]System.Object
0xeb98b  dup
0xeb98c  ldc.i4.0
0xeb98d  ldloc.2
0xeb98e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xeb993  stelem.ref
0xeb994  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xeb999  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xeb99e  throw
0xeb99f  ldloc.0
0xeb9a0  ldloc.2
0xeb9a1  ldarg.3
0xeb9a2  callvirt instance bool Microsoft.Crm.ObjectModel.CustomControlNodeValidationHelper::DoesAnyCustomControlHasFieldLevelControl(class [System.Xml]System.Xml.XPath.IXPathNavigable containerNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0xeb9a7  brfalse.s loc_EB9EF
0xeb9a9  ldnull
0xeb9aa  ldarg.3
0xeb9ab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xeb9b0  ldc.i4.s 0x11
0xeb9b2  ldstr    aCustomcontrolI_2// "CustomControl import default config enc"...
0xeb9b7  ldc.i4.1
0xeb9b8  newarr   [mscorlib]System.Object
0xeb9bd  dup
0xeb9be  ldc.i4.0
0xeb9bf  ldloc.2
0xeb9c0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xeb9c5  stelem.ref
0xeb9c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xeb9cb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeb9d0  ldstr    aCustomcontrolI_2// "CustomControl import default config enc"...
0xeb9d5  ldc.i4.1
0xeb9d6  newarr   [mscorlib]System.Object
0xeb9db  dup
0xeb9dc  ldc.i4.0
0xeb9dd  ldloc.2
0xeb9de  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xeb9e3  stelem.ref
0xeb9e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xeb9e9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xeb9ee  throw
0xeb9ef  ldloc.2
0xeb9f0  ldstr    aControldescrip_6// "//controlDescription"
0xeb9f5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xeb9fa  stloc.3
0xeb9fb  ldloc.3
0xeb9fc  brtrue.s loc_EBA58
0xeb9fe  ldloc.2
0xeb9ff  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xeba04  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0xeba09  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xeba0e  ldc.i4.0
0xeba0f  ble.s    loc_EBA57
0xeba11  ldnull
0xeba12  ldarg.3
0xeba13  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xeba18  ldc.i4.s 0x11
0xeba1a  ldstr    aCustomcontrolI_3// "CustomControl import default config cou"...
0xeba1f  ldc.i4.1
0xeba20  newarr   [mscorlib]System.Object
0xeba25  dup
0xeba26  ldc.i4.0
0xeba27  ldloc.2
0xeba28  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xeba2d  stelem.ref
0xeba2e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xeba33  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeba38  ldstr    aCustomcontrolI_4// "CustomControl import default config enc"...
0xeba3d  ldc.i4.1
0xeba3e  newarr   [mscorlib]System.Object
0xeba43  dup
0xeba44  ldc.i4.0
0xeba45  ldloc.2
0xeba46  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xeba4b  stelem.ref
0xeba4c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xeba51  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xeba56  throw
0xeba57  ret
0xeba58  ldloc.0
0xeba59  ldloc.3
0xeba5a  ldarg.2
0xeba5b  ldarg.3
0xeba5c  callvirt instance void Microsoft.Crm.ObjectModel.CustomControlNodeValidationHelper::Validate(class [System.Xml]System.Xml.XmlNode controlDescriptionNode, int32 entityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0xeba61  ldloc.1
0xeba62  ldloc.3
0xeba63  ldarg.2
0xeba64  ldarg.3
0xeba65  callvirt instance void Microsoft.Crm.ObjectModel.CustomControlParameterValidationHelper::Validate(class [System.Xml]System.Xml.XmlNode controlDescriptionNode, int32 entityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0xeba6a  ret
```
