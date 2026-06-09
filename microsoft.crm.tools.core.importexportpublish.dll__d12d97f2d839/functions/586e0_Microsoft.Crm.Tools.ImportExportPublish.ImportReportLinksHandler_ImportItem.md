# Microsoft.Crm.Tools.ImportExportPublish.ImportReportLinksHandler::ImportItem

- ea: `0x586e0`
- end: `0x588dd`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportReportLinksHandler::ImportItem`
- size: `509`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x35f30`
- `0x586e0`
- `0x588e0`
- `0x63df0`
- `0x68720`
- `0x74460`
- `0x74680`

## string_xrefs

- `0x586e6`: `/ImportExportXml/Reports/ReportLinks`
- `0x586f6`: `./ReportLink`
- `0x5885e`: `Could not update parent report link for the child report {0}`

## pseudocode

```c

```

## disassembly

```asm
0x586e0  ldarg.0
0x586e1  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x586e6  ldstr    aImportexportxm_144// "/ImportExportXml/Reports/ReportLinks"
0x586eb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x586f0  stloc.0
0x586f1  ldloc.0
0x586f2  brtrue.s loc_586F5
0x586f4  ret
0x586f5  ldloc.0
0x586f6  ldstr    aReportlink_0// "./ReportLink"
0x586fb  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x58700  stloc.1
0x58701  ldloc.1
0x58702  brfalse.s loc_5870C
0x58704  ldloc.1
0x58705  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x5870a  brtrue.s loc_58711
0x5870c  leave    loc_588DC
0x58711  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x58716  stloc.2
0x58717  ldloc.1
0x58718  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5871d  stloc.3
0x5871e  br       loc_58831
0x58723  ldloc.3
0x58724  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x58729  castclass [System.Xml]System.Xml.XmlNode
0x5872e  stloc.s  4
0x58730  ldloc.s  4
0x58732  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x58737  ldstr    aDonotimport// "donotimport"
0x5873c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x58741  brfalse.s loc_58763
0x58743  ldloc.s  4
0x58745  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5874a  ldstr    aDonotimport// "donotimport"
0x5874f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x58754  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x58759  call     bool [mscorlib]System.Boolean::Parse(string)
0x5875e  brtrue   loc_58831
0x58763  ldloca.s 5
0x58765  ldloc.s  4
0x58767  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5876c  ldstr    aReportid// "reportid"
0x58771  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x58776  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5877b  call     instance void [mscorlib]System.Guid::.ctor(string)
0x58780  ldloc.s  5
0x58782  stloc.2
0x58783  ldloca.s 6
0x58785  ldloc.s  4
0x58787  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5878c  ldstr    aParentreportid// "parentreportid"
0x58791  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x58796  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5879b  call     instance void [mscorlib]System.Guid::.ctor(string)
0x587a0  ldloc.s  6
0x587a2  ldc.i4.1
0x587a3  newarr   [mscorlib]System.String
0x587a8  dup
0x587a9  ldc.i4.0
0x587aa  ldstr    aReportid// "reportid"
0x587af  stelem.ref
0x587b0  ldarg.0
0x587b1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportLinksHandler::context
0x587b6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.ReportImportExportHelper::RetrieveReport(valuetype [mscorlib]System.Guid reportId, string[] columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x587bb  stloc.s  7
0x587bd  ldloc.s  7
0x587bf  brfalse.s loc_58831
0x587c1  ldloc.s  7
0x587c3  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x587c8  brfalse.s loc_58831
0x587ca  ldarg.0
0x587cb  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportLinksHandler::context
0x587d0  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Report::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x587d5  stloc.s  8
0x587d7  ldloc.s  8
0x587d9  ldstr    aReportid// "reportid"
0x587de  ldarg.0
0x587df  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x587e4  ldloc.s  5
0x587e6  ldarg.0
0x587e7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportLinksHandler::context
0x587ec  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ReportSignatureIdExportImportHandler::GetReportIdForImport(class [System.Xml]System.Xml.XmlDocument importDocument, valuetype [mscorlib]System.Guid reportId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x587f1  box      [mscorlib]System.Guid
0x587f6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x587fb  ldloc.s  8
0x587fd  ldstr    aParentreportid// "parentreportid"
0x58802  ldarg.0
0x58803  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x58808  ldloc.s  6
0x5880a  ldarg.0
0x5880b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportLinksHandler::context
0x58810  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ReportSignatureIdExportImportHandler::GetReportIdForImport(class [System.Xml]System.Xml.XmlDocument importDocument, valuetype [mscorlib]System.Guid reportId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x58815  box      [mscorlib]System.Guid
0x5881a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5881f  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ReportService::.ctor()
0x58824  ldloc.s  8
0x58826  ldarg.0
0x58827  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportLinksHandler::context
0x5882c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x58831  ldloc.3
0x58832  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x58837  brtrue   loc_58723
0x5883c  leave.s  loc_58852
0x5883e  ldloc.3
0x5883f  isinst   [mscorlib]System.IDisposable
0x58844  stloc.s  9
0x58846  ldloc.s  9
0x58848  brfalse.s loc_58851
0x5884a  ldloc.s  9
0x5884c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x58851  endfinally
0x58852  leave    loc_588DC
0x58857  stloc.s  0xA
0x58859  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5885e  ldstr    aCouldNotUpdate// "Could not update parent report link for"...
0x58863  ldc.i4.1
0x58864  newarr   [mscorlib]System.Object
0x58869  dup
0x5886a  ldc.i4.0
0x5886b  ldloc.2
0x5886c  box      [mscorlib]System.Guid
0x58871  stelem.ref
0x58872  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x58877  stloc.s  0xB
0x58879  ldarg.0
0x5887a  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportReportLinksHandler::tracer
0x5887f  ldloc.s  0xB
0x58881  ldloc.s  0xA
0x58883  ldc.i4.3
0x58884  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x58889  ldloc.s  0xA
0x5888b  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException
0x58890  stloc.s  0xC
0x58892  ldloc.s  0xC
0x58894  brfalse.s loc_588A4
0x58896  ldloc.s  0xC
0x58898  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x5889d  call     bool [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReportUtility::IsSafeToShowSrsErrors(int32)
0x588a2  br.s     loc_588A5
0x588a4  ldc.i4.1
0x588a5  stloc.s  0xD
0x588a7  ldarg.0
0x588a8  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x588ad  ldarg.0
0x588ae  ldloc.2
0x588af  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportReportLinksHandler::GetParameterXPath(valuetype [mscorlib]System.Guid id)
0x588b4  ldstr    aFailure// "failure"
0x588b9  ldloc.s  0xA
0x588bb  ldc.i4.0
0x588bc  ldc.i4.1
0x588bd  ldloc.s  0xD
0x588bf  ldc.i4.0
0x588c0  ceq
0x588c2  ldc.i4.0
0x588c3  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, bool replaceExistingResult, bool ignoreInnerException, [opt] int32 crmErrorCode)
0x588c8  ldloc.s  0xB
0x588ca  ldloc.s  0xA
0x588cc  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportReportsException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x588d1  throw
0x588d2  ldloc.1
0x588d3  brfalse.s loc_588DB
0x588d5  ldloc.1
0x588d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x588db  endfinally
0x588dc  ret
```
