# Microsoft.Crm.Tools.ImportExportPublish.PrivilegeObjectTypeCodeExportHandler::ExportItem

- ea: `0x1da50`
- end: `0x1db4f`
- name: `Microsoft.Crm.Tools.ImportExportPublish.PrivilegeObjectTypeCodeExportHandler::ExportItem`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1da50`
- `0x1db50`
- `0x391e0`
- `0x39930`
- `0x3b380`
- `0x3b3c0`

## string_xrefs

- `0x1dad8`: `privilegeobjecttypecode`
- `0x1da81`: `EntityPrivileges`
- `0x1da6d`: `/ImportExportXml/EntityPrivileges`
- `0x1da96`: `privilegeobjecttypecodeslist`
- `0x1dacb`: `privilegeobjecttypecodes`

## pseudocode

```c

```

## disassembly

```asm
0x1da50  ldarg.0
0x1da51  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.PrivilegeObjectTypeCodeExportHandler::_privilegeOtcIdsToExport
0x1da56  brfalse.s loc_1DA65
0x1da58  ldarg.0
0x1da59  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.PrivilegeObjectTypeCodeExportHandler::_privilegeOtcIdsToExport
0x1da5e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x1da63  brtrue.s loc_1DA6A
0x1da65  leave    loc_1DB4E
0x1da6a  ldc.i4.0
0x1da6b  stloc.0
0x1da6c  ldarg.1
0x1da6d  ldstr    aImportexportxm_24// "/ImportExportXml/EntityPrivileges"
0x1da72  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1da77  castclass [System.Xml]System.Xml.XmlElement
0x1da7c  stloc.1
0x1da7d  ldloc.1
0x1da7e  brtrue.s loc_1DA8E
0x1da80  ldarg.1
0x1da81  ldstr    aEntityprivileg// "EntityPrivileges"
0x1da86  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x1da8b  stloc.1
0x1da8c  ldc.i4.1
0x1da8d  stloc.0
0x1da8e  ldarg.0
0x1da8f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.PrivilegeObjectTypeCodeExportHandler::GetPrivilegeOtc()
0x1da94  stloc.2
0x1da95  ldarg.1
0x1da96  ldstr    aPrivilegeobjec_2// "privilegeobjecttypecodeslist"
0x1da9b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x1daa0  stloc.3
0x1daa1  ldloc.2
0x1daa2  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1daa7  ldc.i4.0
0x1daa8  ble.s    loc_1DB15
0x1daaa  ldloc.1
0x1daab  ldloc.3
0x1daac  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x1dab1  pop
0x1dab2  ldloc.2
0x1dab3  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1dab8  stloc.s  4
0x1daba  br.s     loc_1DAF5
0x1dabc  ldloc.s  4
0x1dabe  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1dac3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1dac8  stloc.s  5
0x1daca  ldarg.1
0x1dacb  ldstr    aPrivilegeobjec_3// "privilegeobjecttypecodes"
0x1dad0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x1dad5  stloc.s  6
0x1dad7  ldarg.0
0x1dad8  ldstr    aPrivilegeobjec_0// "privilegeobjecttypecode"
0x1dadd  ldarg.1
0x1dade  ldloc.s  6
0x1dae0  ldloc.s  5
0x1dae2  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x1dae7  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x1daec  ldloc.3
0x1daed  ldloc.s  6
0x1daef  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x1daf4  pop
0x1daf5  ldloc.s  4
0x1daf7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1dafc  brtrue.s loc_1DABC
0x1dafe  leave.s  loc_1DB15
0x1db00  ldloc.s  4
0x1db02  isinst   [mscorlib]System.IDisposable
0x1db07  stloc.s  7
0x1db09  ldloc.s  7
0x1db0b  brfalse.s loc_1DB14
0x1db0d  ldloc.s  7
0x1db0f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1db14  endfinally
0x1db15  ldloc.0
0x1db16  brfalse.s loc_1DB25
0x1db18  ldarg.1
0x1db19  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x1db1e  ldloc.1
0x1db1f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x1db24  pop
0x1db25  leave.s  loc_1DB3E
0x1db27  stloc.s  8
0x1db29  ldarg.0
0x1db2a  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.PrivilegeObjectTypeCodeExportHandler::_tracer
0x1db2f  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::PrivilegeObjectTypeCodesExportErrorMessage
0x1db34  ldloc.s  8
0x1db36  ldc.i4.3
0x1db37  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x1db3c  rethrow
0x1db3e  ldarg.0
0x1db3f  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.PrivilegeObjectTypeCodeExportHandler::_tracer
0x1db44  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::PrivilegeObjectTypeCodesExportSuccessMessage
0x1db49  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x1db4e  ret
```
