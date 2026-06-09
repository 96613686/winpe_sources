# Microsoft.Crm.Tools.ImportExportPublish.PrivilegeExportHandler::ExportItem

- ea: `0x1d8d0`
- end: `0x1d9ac`
- name: `Microsoft.Crm.Tools.ImportExportPublish.PrivilegeExportHandler::ExportItem`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1d8d0`
- `0x1d9b0`
- `0x391e0`
- `0x39930`
- `0x3b380`
- `0x3b3c0`

## string_xrefs

- `0x1d92e`: `privilege`
- `0x1d93b`: `privilege`
- `0x1d8eb`: `EntityPrivileges`
- `0x1d8fd`: `privileges`

## pseudocode

```c

```

## disassembly

```asm
0x1d8d0  ldarg.0
0x1d8d1  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.PrivilegeExportHandler::_privilegeIdsToExport
0x1d8d6  brfalse.s loc_1D8E5
0x1d8d8  ldarg.0
0x1d8d9  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.PrivilegeExportHandler::_privilegeIdsToExport
0x1d8de  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x1d8e3  brtrue.s loc_1D8EA
0x1d8e5  leave    loc_1D9AB
0x1d8ea  ldarg.1
0x1d8eb  ldstr    aEntityprivileg// "EntityPrivileges"
0x1d8f0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x1d8f5  stloc.0
0x1d8f6  ldarg.0
0x1d8f7  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.PrivilegeExportHandler::GetPrivileges()
0x1d8fc  ldarg.1
0x1d8fd  ldstr    aPrivileges// "privileges"
0x1d902  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x1d907  stloc.1
0x1d908  dup
0x1d909  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1d90e  ldc.i4.0
0x1d90f  ble.s    loc_1D919
0x1d911  ldloc.0
0x1d912  ldloc.1
0x1d913  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x1d918  pop
0x1d919  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1d91e  stloc.2
0x1d91f  br.s     loc_1D957
0x1d921  ldloc.2
0x1d922  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1d927  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1d92c  stloc.3
0x1d92d  ldarg.1
0x1d92e  ldstr    aPrivilege_0// "privilege"
0x1d933  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x1d938  stloc.s  4
0x1d93a  ldarg.0
0x1d93b  ldstr    aPrivilege_0// "privilege"
0x1d940  ldarg.1
0x1d941  ldloc.s  4
0x1d943  ldloc.3
0x1d944  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x1d949  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x1d94e  ldloc.1
0x1d94f  ldloc.s  4
0x1d951  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x1d956  pop
0x1d957  ldloc.2
0x1d958  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d95d  brtrue.s loc_1D921
0x1d95f  leave.s  loc_1D975
0x1d961  ldloc.2
0x1d962  isinst   [mscorlib]System.IDisposable
0x1d967  stloc.s  5
0x1d969  ldloc.s  5
0x1d96b  brfalse.s loc_1D974
0x1d96d  ldloc.s  5
0x1d96f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d974  endfinally
0x1d975  ldarg.1
0x1d976  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x1d97b  ldloc.0
0x1d97c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x1d981  pop
0x1d982  leave.s  loc_1D99B
0x1d984  stloc.s  6
0x1d986  ldarg.0
0x1d987  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.PrivilegeExportHandler::_tracer
0x1d98c  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::PrivilegesExportErrorMessage
0x1d991  ldloc.s  6
0x1d993  ldc.i4.3
0x1d994  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x1d999  rethrow
0x1d99b  ldarg.0
0x1d99c  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.PrivilegeExportHandler::_tracer
0x1d9a1  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::PrivilegesExportSuccessMessage
0x1d9a6  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x1d9ab  ret
```
