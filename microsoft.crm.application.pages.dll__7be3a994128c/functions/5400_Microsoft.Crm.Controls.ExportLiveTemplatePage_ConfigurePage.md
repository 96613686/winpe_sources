# Microsoft.Crm.Controls.ExportLiveTemplatePage::ConfigurePage

- ea: `0x5400`
- end: `0x581d`
- name: `Microsoft.Crm.Controls.ExportLiveTemplatePage::ConfigurePage`
- size: `1053`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4a90`
- `0x5050`
- `0x5110`
- `0x5400`
- `0x5820`
- `0x5a00`
- `0x5a20`
- `0x5a40`
- `0x5cd0`
- `0x5e80`
- `0x6370`
- `0x64c0`

## string_xrefs

- `0x540b`: `gridXml`
- `0x5421`: `fetchXml`
- `0x5437`: `layoutXml`
- `0x55f6`: `layoutXml`

## pseudocode

```c

```

## disassembly

```asm
0x5400  ldarg.0
0x5401  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5406  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x540b  ldstr    aGridxml// "gridXml"
0x5410  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5415  stloc.0
0x5416  ldarg.0
0x5417  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x541c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x5421  ldstr    aFetchxml// "fetchXml"
0x5426  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x542b  stloc.1
0x542c  ldarg.0
0x542d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5432  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Params()
0x5437  ldstr    aLayoutxml// "layoutXml"
0x543c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5441  stloc.2
0x5442  ldarg.0
0x5443  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5448  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x544d  ldstr    aExporttype// "exportType"
0x5452  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5457  stloc.3
0x5458  ldloca.s 4
0x545a  ldarg.0
0x545b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5460  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x5465  ldstr    aViewid// "viewid"
0x546a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x546f  call     instance void [mscorlib]System.Guid::.ctor(string)
0x5474  ldarg.0
0x5475  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x547a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Params()
0x547f  ldstr    aViewtype// "viewtype"
0x5484  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5489  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x548e  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x5493  stloc.s  5
0x5495  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x549a  stloc.s  6
0x549c  ldloc.3
0x549d  ldstr    aList// "list"
0x54a2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54a7  brfalse.s loc_54B1
0x54a9  ldstr    aDynamicxlsx// "dynamicXlsx"
0x54ae  stloc.3
0x54af  br.s     loc_54C4
0x54b1  ldloc.3
0x54b2  ldstr    aPivot// "pivot"
0x54b7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54bc  brfalse.s loc_54C4
0x54be  ldstr    aPivotxlsx// "pivotXlsx"
0x54c3  stloc.3
0x54c4  ldloc.3
0x54c5  ldstr    aDynamicxlsx// "dynamicXlsx"
0x54ca  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54cf  brfalse.s loc_54E0
0x54d1  ldarg.0
0x54d2  ldloc.0
0x54d3  ldloc.1
0x54d4  ldloc.2
0x54d5  ldloc.s  4
0x54d7  ldloc.s  5
0x54d9  ldc.i4.0
0x54da  call     instance void Microsoft.Crm.Controls.ExportLiveTemplatePage::ConfigurePageForDynamicXlsx(string gridXml, string fetchXml, string layoutXml, valuetype [mscorlib]System.Guid viewId, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType viewType, valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ExportDynamicToExcelType exportType)
0x54df  ret
0x54e0  ldloc.3
0x54e1  ldstr    aPivotxlsx// "pivotXlsx"
0x54e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54eb  brfalse.s loc_54FC
0x54ed  ldarg.0
0x54ee  ldloc.0
0x54ef  ldloc.1
0x54f0  ldloc.2
0x54f1  ldloc.s  4
0x54f3  ldloc.s  5
0x54f5  ldc.i4.1
0x54f6  call     instance void Microsoft.Crm.Controls.ExportLiveTemplatePage::ConfigurePageForDynamicXlsx(string gridXml, string fetchXml, string layoutXml, valuetype [mscorlib]System.Guid viewId, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType viewType, valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ExportDynamicToExcelType exportType)
0x54fb  ret
0x54fc  ldarg.0
0x54fd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5502  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x5507  ldstr    aExporttype// "exportType"
0x550c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5511  ldstr    aPivot// "pivot"
0x5516  call     bool [mscorlib]System.String::op_Equality(string, string)
0x551b  stloc.s  7
0x551d  ldarg.0
0x551e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5523  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x5528  ldstr    aUsesqlquery// "useSqlQuery"
0x552d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5532  ldstr    a1// "1"
0x5537  call     bool [mscorlib]System.String::op_Equality(string, string)
0x553c  stloc.s  8
0x553e  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x5543  stloc.s  9
0x5545  ldloc.s  9
0x5547  ldc.i4.1
0x5548  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x554d  ldloc.s  9
0x554f  ldstr    asc_11B71A// "  "
0x5554  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_IndentChars(string)
0x5559  ldloc.s  9
0x555b  ldc.i4.1
0x555c  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_ConformanceLevel(valuetype [System.Xml]System.Xml.ConformanceLevel)
0x5561  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x5566  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x556b  stloc.s  0xA
0x556d  ldloc.s  0xA
0x556f  ldloc.s  9
0x5571  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.TextWriter, class [System.Xml]System.Xml.XmlWriterSettings)
0x5576  stloc.s  0xB
0x5578  ldarg.0
0x5579  ldloc.s  0xB
0x557b  ldloc.s  7
0x557d  ldloc.s  8
0x557f  call     instance void Microsoft.Crm.Controls.ExportLiveTemplatePage::WriteWorkbookHeader(class [System.Xml]System.Xml.XmlWriter xmlWriter, bool isExportPivot, bool useSqlQuery)
0x5584  ldloc.s  4
0x5586  ldloc.s  5
0x5588  call     string Microsoft.Crm.Controls.ExportLiveTemplatePage::GetViewName(valuetype [mscorlib]System.Guid viewId, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType viewType)
0x558d  stloc.s  0xC
0x558f  ldstr    aXml_0// ".xml"
0x5594  stloc.s  0xD
0x5596  ldloc.s  0xC
0x5598  brfalse.s loc_55B3
0x559a  ldloc.s  0xC
0x559c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x55a1  ldc.i4.0
0x55a2  ble.s    loc_55B3
0x55a4  ldloc.s  0xC
0x55a6  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GenerateValidExcelWorkSheetTitle(string)
0x55ab  stloc.s  0xE
0x55ad  ldloc.s  0xC
0x55af  stloc.s  0xF
0x55b1  br.s     loc_55CB
0x55b3  ldstr    aSheet1// "Sheet1"
0x55b8  stloc.s  0xE
0x55ba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x55bf  ldstr    aExporttoexcelF// "ExportToExcel.FileName"
0x55c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x55c9  stloc.s  0xF
0x55cb  ldloc.s  8
0x55cd  brfalse  loc_5779
0x55d2  ldloc.1
0x55d3  ldstr    aNoLockFalse// "no-lock=\"false\""
0x55d8  ldstr    aNoLockTrue// "no-lock=\"true\""
0x55dd  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x55e2  stloc.1
0x55e3  ldloc.1
0x55e4  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x55e9  stloc.s  0x11
0x55eb  ldarg.0
0x55ec  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x55f1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x55f6  ldstr    aLayoutxml// "layoutXml"
0x55fb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5600  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5605  stloc.s  0x12
0x5607  ldloc.s  0x11
0x5609  ldstr    aFetchEntityNam// "/fetch/entity/@name"
0x560e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5613  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5618  stloc.s  0x13
0x561a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x561f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5624  ldloc.s  0x13
0x5626  ldc.i4.1
0x5627  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x562c  stloc.s  0x14
0x562e  ldloc.s  0x12
0x5630  ldstr    aGridRowCellCon// "grid/row/cell[contains(@name, \".\")]"
0x5635  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x563a  ldnull
0x563b  cgt.un
0x563d  brfalse.s loc_565F
0x563f  ldloc.s  0x12
0x5641  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x5646  ldloc.1
0x5647  ldloc.s  0x14
0x5649  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x564e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5653  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ColumnUtility::PopulateLayoutWithRelationshipInfo(string, string, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5658  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x565d  stloc.s  0x12
0x565f  ldloc.s  0x14
0x5661  ldloc.s  0x11
0x5663  ldloc.s  0x12
0x5665  newobj   instance void Microsoft.Crm.Controls.SqlExportColumnListBuilder::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata primaryEntity, class [System.Xml]System.Xml.XmlDocument fetchXmlDocument, class [System.Xml]System.Xml.XmlDocument layoutXmlDocument)
0x566a  stloc.s  0x15
0x566c  ldloc.s  7
0x566e  brtrue.s loc_5679
0x5670  ldloc.s  0x15
0x5672  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column> Microsoft.Crm.Controls.ExcelColumnListBuilder::get_OrderedColumnListForWorksheet()
0x5677  br.s     loc_5680
0x5679  ldloc.s  0x15
0x567b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column> Microsoft.Crm.Controls.SqlExportColumnListBuilder::get_OrderedColumnListForPivotTable()
0x5680  stloc.s  0x16
0x5682  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x5687  ldloc.s  6
0x5689  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x568e  ldloc.s  6
0x5690  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x5695  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaxRecordsForExportToExcel()
0x569a  stloc.s  0x17
0x569c  ldloc.s  0x11
0x569e  ldstr    aFetch// "/fetch"
0x56a3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x56a8  castclass [System.Xml]System.Xml.XmlElement
0x56ad  dup
0x56ae  ldstr    aPage// "page"
0x56b3  ldstr    a1// "1"
0x56b8  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x56bd  dup
0x56be  ldstr    aCount// "count"
0x56c3  ldloca.s 0x17
0x56c5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x56ca  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x56cf  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x56d4  ldstr    aReturntotalrec// "returntotalrecordcount"
0x56d9  ldstr    aFalse// "false"
0x56de  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x56e3  ldloc.s  6
0x56e5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x56ea  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmDirectSqlConnection::GetDatabaseServerName(valuetype [mscorlib]System.Guid)
0x56ef  stloc.s  0x18
0x56f1  ldloc.s  6
0x56f3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x56f8  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationConfig::AlternateExportSqlServerName(valuetype [mscorlib]System.Guid)
0x56fd  stloc.s  0x19
0x56ff  ldloc.s  0x19
0x5701  brfalse.s loc_5711
0x5703  ldloc.s  0x19
0x5705  callvirt instance int32 [mscorlib]System.String::get_Length()
0x570a  ldc.i4.0
0x570b  ble.s    loc_5711
0x570d  ldloc.s  0x19
0x570f  stloc.s  0x18
0x5711  ldloc.s  0x11
0x5713  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x5718  ldc.i4.1
0x5719  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x571e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveReportSqlFromQuery(string, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5723  stloc.s  0x1A
0x5725  ldstr    aDriverSqlServe// "DRIVER=SQL Server;APP=Microsoft Office "...
0x572a  ldloc.s  0x18
0x572c  ldstr    aDatabase// ";DATABASE="
0x5731  ldloc.s  6
0x5733  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5738  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmDirectSqlConnection::GetDatabaseName(valuetype [mscorlib]System.Guid)
0x573d  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x5742  stloc.s  0x1B
0x5744  ldarg.0
0x5745  ldloc.s  0xB
0x5747  ldloc.s  0xE
0x5749  call     instance void Microsoft.Crm.Controls.ExportLiveTemplatePage::WriteWorksheetHeader(class [System.Xml]System.Xml.XmlWriter xmlWriter, string sheetName)
0x574e  ldloc.s  7
0x5750  brfalse.s loc_5762
0x5752  ldarg.0
0x5753  ldloc.s  0xB
0x5755  ldloc.s  0x16
0x5757  ldloc.s  0x1A
0x5759  ldloc.s  0x1B
0x575b  call     instance void Microsoft.Crm.Controls.ExportLiveTemplatePage::WriteSqlPivotSheet(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column> columnList, string sql, string connection)
0x5760  br.s     loc_5770
0x5762  ldarg.0
0x5763  ldloc.s  0xB
0x5765  ldloc.s  0x16
0x5767  ldloc.s  0x1A
0x5769  ldloc.s  0x1B
0x576b  call     instance void Microsoft.Crm.Controls.ExportLiveTemplatePage::WriteSqlListSheet(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column> columnList, string sql, string connection)
0x5770  ldloc.s  0xB
0x5772  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x5777  br.s     loc_5797
0x5779  ldarg.0
0x577a  ldloc.s  0xB
0x577c  ldloc.s  0xE
0x577e  call     instance void Microsoft.Crm.Controls.ExportLiveTemplatePage::WriteWorksheetHeader(class [System.Xml]System.Xml.XmlWriter xmlWriter, string sheetName)
0x5783  ldarg.0
0x5784  ldloc.s  0xB
0x5786  ldloc.s  7
0x5788  ldloc.0
0x5789  ldloc.1
0x578a  ldloc.2
0x578b  call     instance void Microsoft.Crm.Controls.ExportLiveTemplatePage::WriteWebQuerySheet(class [System.Xml]System.Xml.XmlWriter xmlWriter, bool isExportPivot, string gridXml, string fetchXml, string layoutXml)
0x5790  ldloc.s  0xB
0x5792  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x5797  ldloc.s  0xB
0x5799  ldstr    aWorkbook// "</Workbook>"
0x579e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x57a3  ldloc.s  0xB
0x57a5  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x57aa  ldarg.0
0x57ab  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x57b0  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x57b5  ldarg.0
0x57b6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x57bb  ldstr    aApplicationVnd// "application/vnd.ms-excel"
0x57c0  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
  ... truncated ...
```
