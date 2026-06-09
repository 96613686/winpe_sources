# Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::CreateOrUpdateReport

- ea: `0x57aa0`
- end: `0x57d16`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::CreateOrUpdateReport`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x577f0`

## callees

- `0x4ded0`
- `0x4dee0`
- `0x4df00`
- `0x4df10`
- `0x57aa0`
- `0x58cd0`
- `0x58d20`
- `0x8f0b0`
- `0x94c90`

## string_xrefs

- `0x57ac3`: `createdinmajorversion`
- `0x57ad8`: `createdinmajorversion`
- `0x57b04`: `createdinmajorversion`
- `0x57c41`: `customreportxml`
- `0x57cdd`: `customreportxml`

## pseudocode

```c

```

## disassembly

```asm
0x57aa0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ReportService::.ctor()
0x57aa5  stloc.0
0x57aa6  ldc.i4   0x238C
0x57aab  call     class Microsoft.Crm.Tools.ImportExportPublish.IXmlToBusinessEntityConvertor Microsoft.Crm.Tools.ImportExportPublish.XmlToBusinessEntityConvertorFactory::GetConvertor(int32 objectTypeCode)
0x57ab0  ldarg.0
0x57ab1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x57ab6  ldarg.1
0x57ab7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Tools.ImportExportPublish.IXmlToBusinessEntityConvertor::GetBusinessEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlNode node)
0x57abc  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Report
0x57ac1  stloc.1
0x57ac2  ldloc.1
0x57ac3  ldstr    aCreatedinmajor// "createdinmajorversion"
0x57ac8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x57acd  brfalse.s loc_57B14
0x57acf  ldarg.0
0x57ad0  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::_isInternalSolution
0x57ad5  brfalse.s loc_57B03
0x57ad7  ldloc.1
0x57ad8  ldstr    aCreatedinmajor// "createdinmajorversion"
0x57add  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.VersionService::.ctor()
0x57ae2  ldarg.0
0x57ae3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x57ae8  call     instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.VersionService::RetrieveVersion(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x57aed  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x57af2  call     instance int32 [mscorlib]System.Version::get_Major()
0x57af7  box      [mscorlib]System.Int32
0x57afc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x57b01  br.s     loc_57B14
0x57b03  ldloc.1
0x57b04  ldstr    aCreatedinmajor// "createdinmajorversion"
0x57b09  ldc.i4.0
0x57b0a  box      [mscorlib]System.Int32
0x57b0f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x57b14  ldarg.0
0x57b15  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::_isInternalSolution
0x57b1a  brfalse.s loc_57B4E
0x57b1c  ldloc.1
0x57b1d  ldstr    aLanguagecode// "languagecode"
0x57b22  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57b27  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57b2c  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x57b31  ldloc.1
0x57b32  ldstr    aReportnameonsr// "reportnameonsrs"
0x57b37  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57b3c  call     string [mscorlib]System.String::Concat(object, object)
0x57b41  stloc.3
0x57b42  ldloc.1
0x57b43  ldstr    aReportnameonsr// "reportnameonsrs"
0x57b48  ldloc.3
0x57b49  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x57b4e  ldarg.0
0x57b4f  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::_isInternalSolution
0x57b54  brfalse.s loc_57B77
0x57b56  ldloc.1
0x57b57  ldstr    aIntroducedvers// "introducedversion"
0x57b5c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x57b61  brfalse.s loc_57B77
0x57b63  ldstr    a50// "5.0"
0x57b68  stloc.s  4
0x57b6a  ldloc.1
0x57b6b  ldstr    aIntroducedvers// "introducedversion"
0x57b70  ldloc.s  4
0x57b72  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x57b77  ldc.i4.0
0x57b78  stloc.2
0x57b79  ldloc.1
0x57b7a  ldstr    aReporttypecode// "reporttypecode"
0x57b7f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57b84  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57b89  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x57b8e  ldc.i4.1
0x57b8f  beq.s    loc_57BAC
0x57b91  ldloc.1
0x57b92  ldstr    aReporttypecode// "reporttypecode"
0x57b97  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57b9c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57ba1  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x57ba6  ldc.i4.2
0x57ba7  bne.un   loc_57C72
0x57bac  ldarg.1
0x57bad  ldstr    aExportedfilena// "ExportedFileName"
0x57bb2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x57bb7  stloc.s  5
0x57bb9  ldloc.s  5
0x57bbb  brfalse  loc_57C72
0x57bc0  ldloc.s  5
0x57bc2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x57bc7  stloc.s  6
0x57bc9  ldloc.s  6
0x57bcb  ldloc.s  6
0x57bcd  ldstr    asc_9A456// "/"
0x57bd2  ldc.i4.4
0x57bd3  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x57bd8  ldc.i4.1
0x57bd9  add
0x57bda  callvirt instance string [mscorlib]System.String::Substring(int32)
0x57bdf  stloc.s  7
0x57be1  ldstr    aReports_1// "/Reports/"
0x57be6  ldloc.s  7
0x57be8  call     string [mscorlib]System.String::Concat(string, string)
0x57bed  stloc.s  6
0x57bef  ldarg.0
0x57bf0  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::_filesToImport
0x57bf5  ldloc.s  6
0x57bf7  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet::ContainsFile(string fileName)
0x57bfc  brfalse.s loc_57C72
0x57bfe  ldnull
0x57bff  stloc.s  8
0x57c01  ldloc.1
0x57c02  ldstr    aReporttypecode// "reporttypecode"
0x57c07  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57c0c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57c11  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x57c16  ldc.i4.1
0x57c17  bne.un.s loc_57C54
0x57c19  ldarg.0
0x57c1a  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::_filesToImport
0x57c1f  ldloc.s  6
0x57c21  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet::LeaseBufferForFileAsUtf8EncodedString(string fileName)
0x57c26  stloc.s  8
0x57c28  ldloc.1
0x57c29  ldstr    aIscustomreport// "iscustomreport"
0x57c2e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57c33  unbox.any [mscorlib]System.Boolean
0x57c38  brtrue.s loc_57C41
0x57c3a  ldstr    aBodytext// "bodytext"
0x57c3f  br.s     loc_57C46
0x57c41  ldstr    aCustomreportxm// "customreportxml"
0x57c46  stloc.s  9
0x57c48  ldloc.1
0x57c49  ldloc.s  9
0x57c4b  ldloc.s  8
0x57c4d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x57c52  br.s     loc_57C70
0x57c54  ldarg.0
0x57c55  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::_filesToImport
0x57c5a  ldloc.s  6
0x57c5c  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet::LeaseBufferForFileAsBase64EncodedString(string fileName)
0x57c61  stloc.s  8
0x57c63  ldloc.1
0x57c64  ldstr    aBodybinary// "bodybinary"
0x57c69  ldloc.s  8
0x57c6b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x57c70  ldc.i4.1
0x57c71  stloc.2
0x57c72  ldarg.2
0x57c73  brtrue.s loc_57CA7
0x57c75  ldloc.1
0x57c76  ldstr    aIscustomreport// "iscustomreport"
0x57c7b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57c80  unbox.any [mscorlib]System.Boolean
0x57c85  brfalse.s loc_57C97
0x57c87  ldloc.0
0x57c88  ldloc.1
0x57c89  ldarg.0
0x57c8a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x57c8f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ReportServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::CreateInternalFromTemplate(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Report, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x57c94  pop
0x57c95  br.s     loc_57D07
0x57c97  ldloc.0
0x57c98  ldloc.1
0x57c99  ldarg.0
0x57c9a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x57c9f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x57ca4  pop
0x57ca5  br.s     loc_57D07
0x57ca7  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ReportPreImportHandler::.ctor()
0x57cac  ldloc.1
0x57cad  ldarg.2
0x57cae  ldarg.0
0x57caf  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x57cb4  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ReportPreImportHandler::ExecutePreUpdateSteps(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity newEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity oldEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57cb9  ldloc.1
0x57cba  ldstr    aIscustomreport// "iscustomreport"
0x57cbf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57cc4  unbox.any [mscorlib]System.Boolean
0x57cc9  brfalse.s loc_57CFA
0x57ccb  ldloc.0
0x57ccc  ldloc.1
0x57ccd  ldstr    aReportid// "reportid"
0x57cd2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57cd7  unbox.any [mscorlib]System.Guid
0x57cdc  ldloc.1
0x57cdd  ldstr    aCustomreportxm// "customreportxml"
0x57ce2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57ce7  castclass [mscorlib]System.String
0x57cec  ldc.i4.1
0x57ced  ldarg.0
0x57cee  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x57cf3  callvirt instance void class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ReportServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::UpdateFromTemplate(valuetype [mscorlib]System.Guid, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x57cf8  br.s     loc_57D07
0x57cfa  ldloc.0
0x57cfb  ldloc.1
0x57cfc  ldarg.0
0x57cfd  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x57d02  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x57d07  ldloc.2
0x57d08  brfalse.s loc_57D15
0x57d0a  ldarg.0
0x57d0b  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::_filesToImport
0x57d10  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet::TerminateLease()
0x57d15  ret
```
