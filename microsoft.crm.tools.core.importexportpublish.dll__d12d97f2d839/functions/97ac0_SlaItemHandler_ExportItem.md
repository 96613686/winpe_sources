# SlaItemHandler::ExportItem

- ea: `0x97ac0`
- end: `0x97d4c`
- name: `SlaItemHandler::ExportItem`
- size: `652`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x39770`
- `0x39ac0`
- `0x3b380`
- `0x3b3c0`
- `0x97ac0`

## string_xrefs

- `0x97bb9`: `applicablewhenxml`
- `0x97bbf`: `applicablewhenxml`
- `0x97bd6`: `successconditionsxml`
- `0x97bdc`: `successconditionsxml`

## pseudocode

```c

```

## disassembly

```asm
0x97ac0  ldarg.0
0x97ac1  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection SlaItemHandler::_entityCollection
0x97ac6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x97acb  ldc.i4.0
0x97acc  bgt.s    loc_97ACF
0x97ace  ret
0x97acf  nop
0x97ad0  ldarg.1
0x97ad1  ldstr    aSlaitems// "SlaItems"
0x97ad6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x97adb  stloc.0
0x97adc  ldarg.0
0x97add  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection SlaItemHandler::_entityCollection
0x97ae2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x97ae7  stloc.1
0x97ae8  br       loc_97CA6
0x97aed  ldloc.1
0x97aee  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x97af3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x97af8  stloc.2
0x97af9  ldarg.0
0x97afa  ldflda   valuetype [mscorlib]System.Guid SlaItemHandler::_reportId
0x97aff  ldloc.2
0x97b00  ldstr    aSlaid// "slaid"
0x97b05  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97b0a  unbox.any [mscorlib]System.Guid
0x97b0f  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x97b14  brfalse  loc_97CA6
0x97b19  ldarg.1
0x97b1a  ldstr    aSlaitem// "SlaItem"
0x97b1f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x97b24  stloc.3
0x97b25  ldarg.0
0x97b26  ldarg.1
0x97b27  ldloc.3
0x97b28  ldstr    aSlaid// "slaid"
0x97b2d  ldloc.2
0x97b2e  ldstr    aSlaid// "slaid"
0x97b33  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97b38  callvirt instance string [mscorlib]System.Object::ToString()
0x97b3d  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97b42  ldarg.0
0x97b43  ldarg.1
0x97b44  ldloc.3
0x97b45  ldstr    aSlaitemid// "slaitemid"
0x97b4a  ldloc.2
0x97b4b  ldstr    aSlaitemid// "slaitemid"
0x97b50  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97b55  callvirt instance string [mscorlib]System.Object::ToString()
0x97b5a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97b5f  ldarg.0
0x97b60  ldarg.1
0x97b61  ldloc.3
0x97b62  ldstr    aRelatedfield// "relatedfield"
0x97b67  ldloc.2
0x97b68  ldstr    aRelatedfield// "relatedfield"
0x97b6d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97b72  castclass [mscorlib]System.String
0x97b77  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97b7c  ldarg.0
0x97b7d  ldarg.1
0x97b7e  ldloc.3
0x97b7f  ldstr    aName// "name"
0x97b84  ldloc.2
0x97b85  ldstr    aName// "name"
0x97b8a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97b8f  castclass [mscorlib]System.String
0x97b94  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97b99  ldarg.0
0x97b9a  ldarg.1
0x97b9b  ldloc.3
0x97b9c  ldstr    aDescription// "description"
0x97ba1  ldloc.2
0x97ba2  ldstr    aDescription// "description"
0x97ba7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97bac  castclass [mscorlib]System.String
0x97bb1  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97bb6  ldarg.0
0x97bb7  ldarg.1
0x97bb8  ldloc.3
0x97bb9  ldstr    aApplicablewhen// "applicablewhenxml"
0x97bbe  ldloc.2
0x97bbf  ldstr    aApplicablewhen// "applicablewhenxml"
0x97bc4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97bc9  castclass [mscorlib]System.String
0x97bce  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97bd3  ldarg.0
0x97bd4  ldarg.1
0x97bd5  ldloc.3
0x97bd6  ldstr    aSuccessconditi// "successconditionsxml"
0x97bdb  ldloc.2
0x97bdc  ldstr    aSuccessconditi// "successconditionsxml"
0x97be1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97be6  castclass [mscorlib]System.String
0x97beb  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97bf0  ldarg.0
0x97bf1  ldarg.1
0x97bf2  ldloc.3
0x97bf3  ldstr    aSequencenumber_0// "sequencenumber"
0x97bf8  ldloc.2
0x97bf9  ldstr    aSequencenumber_0// "sequencenumber"
0x97bfe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97c03  callvirt instance string [mscorlib]System.Object::ToString()
0x97c08  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97c0d  ldarg.0
0x97c0e  ldarg.1
0x97c0f  ldloc.3
0x97c10  ldstr    aWorkflowid_0// "workflowid"
0x97c15  ldloc.2
0x97c16  ldstr    aWorkflowid_0// "workflowid"
0x97c1b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97c20  callvirt instance string [mscorlib]System.Object::ToString()
0x97c25  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97c2a  ldarg.0
0x97c2b  ldarg.1
0x97c2c  ldloc.3
0x97c2d  ldstr    aFailureafter// "failureafter"
0x97c32  ldloc.2
0x97c33  ldstr    aFailureafter// "failureafter"
0x97c38  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97c3d  callvirt instance string [mscorlib]System.Object::ToString()
0x97c42  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97c47  ldarg.0
0x97c48  ldarg.1
0x97c49  ldloc.3
0x97c4a  ldstr    aWarnafter// "warnafter"
0x97c4f  ldloc.2
0x97c50  ldstr    aWarnafter// "warnafter"
0x97c55  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97c5a  callvirt instance string [mscorlib]System.Object::ToString()
0x97c5f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97c64  ldarg.0
0x97c65  ldarg.1
0x97c66  ldloc.3
0x97c67  ldstr    aSlaitemid// "slaitemid"
0x97c6c  ldloc.2
0x97c6d  ldstr    aSlaitemid// "slaitemid"
0x97c72  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97c77  callvirt instance string [mscorlib]System.Object::ToString()
0x97c7c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributeNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97c81  ldarg.0
0x97c82  ldarg.1
0x97c83  ldloc.3
0x97c84  ldstr    aName// "name"
0x97c89  ldloc.2
0x97c8a  ldstr    aName// "name"
0x97c8f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x97c94  castclass [mscorlib]System.String
0x97c99  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributeNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x97c9e  ldloc.0
0x97c9f  ldloc.3
0x97ca0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x97ca5  pop
0x97ca6  ldloc.1
0x97ca7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x97cac  brtrue   loc_97AED
0x97cb1  leave.s  loc_97CC7
0x97cb3  ldloc.1
0x97cb4  isinst   [mscorlib]System.IDisposable
0x97cb9  stloc.s  4
0x97cbb  ldloc.s  4
0x97cbd  brfalse.s loc_97CC6
0x97cbf  ldloc.s  4
0x97cc1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x97cc6  endfinally
0x97cc7  ldarg.0
0x97cc8  ldfld    class [System.Xml]System.Xml.XmlNode SlaItemHandler::_reportNode
0x97ccd  ldloc.0
0x97cce  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x97cd3  pop
0x97cd4  leave.s  loc_97D14
0x97cd6  stloc.s  5
0x97cd8  ldarg.0
0x97cd9  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer SlaItemHandler::tracer
0x97cde  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x97ce3  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::SlaItemExportFailureMessage
0x97ce8  ldc.i4.2
0x97ce9  newarr   [mscorlib]System.Object
0x97cee  dup
0x97cef  ldc.i4.0
0x97cf0  ldarg.0
0x97cf1  ldfld    string SlaItemHandler::_reportName
0x97cf6  stelem.ref
0x97cf7  dup
0x97cf8  ldc.i4.1
0x97cf9  ldarg.0
0x97cfa  ldfld    valuetype [mscorlib]System.Guid SlaItemHandler::_reportId
0x97cff  box      [mscorlib]System.Guid
0x97d04  stelem.ref
0x97d05  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x97d0a  ldloc.s  5
0x97d0c  ldc.i4.1
0x97d0d  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x97d12  rethrow
0x97d14  ldarg.0
0x97d15  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer SlaItemHandler::tracer
0x97d1a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x97d1f  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::SlaItemExportSuccessMessage
0x97d24  ldc.i4.2
0x97d25  newarr   [mscorlib]System.Object
0x97d2a  dup
0x97d2b  ldc.i4.0
0x97d2c  ldarg.0
0x97d2d  ldfld    string SlaItemHandler::_reportName
0x97d32  stelem.ref
0x97d33  dup
0x97d34  ldc.i4.1
0x97d35  ldarg.0
0x97d36  ldfld    valuetype [mscorlib]System.Guid SlaItemHandler::_reportId
0x97d3b  box      [mscorlib]System.Guid
0x97d40  stelem.ref
0x97d41  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x97d46  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x97d4b  ret
```
