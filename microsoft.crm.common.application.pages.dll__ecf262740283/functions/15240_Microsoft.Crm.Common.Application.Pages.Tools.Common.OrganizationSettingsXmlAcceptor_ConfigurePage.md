# Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::ConfigurePage

- ea: `0x15240`
- end: `0x1568c`
- name: `Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::ConfigurePage`
- size: `1100`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x15240`
- `0x156d0`
- `0x15850`
- `0x15870`
- `0x158e0`
- `0x15960`
- `0x15a60`
- `0x15e10`
- `0x16000`
- `0x160f0`

## string_xrefs

- `0x15248`: `text/xml`
- `0x154a8`: `Updated organization settings.`
- `0x154de`: `Flushing SiteMap cache.`
- `0x15513`: `Flushing Metadata cache.`
- `0x15549`: `Flushed Metadata cache.`
- `0x15569`: `//organization/isreadauditenabled`
- `0x155a9`: `IsReadAuditEnabled`
- `0x15603`: `UpdateAuditSettings`

## pseudocode

```c

```

## disassembly

```asm
0x15240  ldnull
0x15241  stloc.0
0x15242  ldarg.0
0x15243  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x15248  ldstr    aTextXml// "text/xml"
0x1524d  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x15252  ldarg.0
0x15253  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x15258  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1525d  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x15262  stloc.1
0x15263  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x15268  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1526d  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x15272  ldstr    aOrganizationse// "OrganizationSettings received from clie"...
0x15277  ldc.i4.1
0x15278  newarr   [mscorlib]System.Object
0x1527d  dup
0x1527e  ldc.i4.0
0x1527f  ldloc.1
0x15280  stelem.ref
0x15281  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x15286  ldloc.1
0x15287  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x1528c  stloc.2
0x1528d  ldloc.2
0x1528e  ldstr    aOrganizationRe// "//organization/reportcategories"
0x15293  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15298  stloc.0
0x15299  ldloc.0
0x1529a  brfalse.s loc_152B0
0x1529c  ldloc.0
0x1529d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x152a2  ldloc.0
0x152a3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x152a8  pop
0x152a9  ldloc.2
0x152aa  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x152af  stloc.1
0x152b0  ldloc.2
0x152b1  ldstr    aOrganizationAu// "//organization/auditareas"
0x152b6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x152bb  stloc.3
0x152bc  ldloc.3
0x152bd  brfalse.s loc_152D3
0x152bf  ldloc.3
0x152c0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x152c5  ldloc.3
0x152c6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x152cb  pop
0x152cc  ldloc.2
0x152cd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x152d2  stloc.1
0x152d3  ldloc.2
0x152d4  ldstr    aOrganizationRe_0// "//organization/RestoreToDefault"
0x152d9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x152de  stloc.s  4
0x152e0  ldloc.s  4
0x152e2  brfalse.s loc_15325
0x152e4  ldloc.s  4
0x152e6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x152eb  dup
0x152ec  ldloc.s  4
0x152ee  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x152f3  pop
0x152f4  ldloc.2
0x152f5  ldstr    aIsappointmenta// "isappointmentattachmentsyncenabled"
0x152fa  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x152ff  stloc.s  0xC
0x15301  ldloc.s  0xC
0x15303  ldarg.0
0x15304  call     instance string Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::GetApptAttachmentDefaultSyncValue()
0x15309  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x1530e  ldloc.s  0xC
0x15310  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x15315  pop
0x15316  ldloc.2
0x15317  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x1531c  stloc.1
0x1531d  ldarg.0
0x1531e  ldloc.s  4
0x15320  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::RestoreToDefault(class [System.Xml]System.Xml.XmlNode restoreToDefaultNode)
0x15325  ldloc.2
0x15326  ldstr    aOrganizationSy// "//organization/SyncAttributes"
0x1532b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15330  stloc.s  5
0x15332  ldloc.s  5
0x15334  brfalse.s loc_15354
0x15336  ldloc.s  5
0x15338  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x1533d  ldloc.s  5
0x1533f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x15344  pop
0x15345  ldloc.2
0x15346  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x1534b  stloc.1
0x1534c  ldarg.0
0x1534d  ldloc.s  5
0x1534f  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::SaveSyncMappingChanges(class [System.Xml]System.Xml.XmlNode syncAttributesNode)
0x15354  ldloc.2
0x15355  ldstr    aOrganizationIs// "//organization/isappointmentattachments"...
0x1535a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1535f  stloc.s  6
0x15361  ldloc.s  6
0x15363  brfalse.s loc_1536D
0x15365  ldarg.0
0x15366  ldloc.s  6
0x15368  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UpdateSyncMappingApptAttachment(class [System.Xml]System.Xml.XmlNode apptAttachmentNode)
0x1536d  ldloc.2
0x1536e  ldstr    aOrganizationDe// "//organization/defaultemailserverprofil"...
0x15373  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15378  stloc.s  7
0x1537a  ldloc.2
0x1537b  ldstr    aOrganizationDe_0// "//organization/defaultemailsettings"
0x15380  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15385  stloc.s  8
0x15387  ldloc.s  7
0x15389  brtrue.s loc_1538F
0x1538b  ldloc.s  8
0x1538d  brfalse.s loc_15399
0x1538f  ldarg.0
0x15390  ldloc.s  7
0x15392  ldloc.s  8
0x15394  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::ValidateEmailProfileAndSettings(class [System.Xml]System.Xml.XmlNode defaultEmailServerProfileNode, class [System.Xml]System.Xml.XmlNode defaultEmailSettingsNode)
0x15399  ldarg.0
0x1539a  call     instance bool Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::IsAutoNumberingPage()
0x1539f  brfalse.s loc_153B7
0x153a1  ldarg.0
0x153a2  ldloc.2
0x153a3  ldstr    aOrganization_0// "//organization"
0x153a8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x153ad  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::HandleAutoNumberedAttributes(class [System.Xml]System.Xml.XmlNode organizationNode)
0x153b2  br       loc_15554
0x153b7  ldloc.2
0x153b8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x153bd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x153c2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x153c7  brtrue   loc_15554
0x153cc  ldstr    aOrganization// "organization"
0x153d1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x153d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x153db  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x153e0  stloc.s  0xD
0x153e2  ldloc.2
0x153e3  ldstr    aOrganizationEn// "//organization/enablemicrosoftflowinteg"...
0x153e8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x153ed  stloc.s  0xE
0x153ef  ldsfld   string [mscorlib]System.String::Empty
0x153f4  stloc.s  0xF
0x153f6  ldloc.s  0xE
0x153f8  brfalse.s loc_1546B
0x153fa  ldloc.2
0x153fb  ldstr    aOrganizationMi// "//organization/microsoftflowenvironment"
0x15400  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15405  stloc.s  0x10
0x15407  ldloc.s  0x10
0x15409  brfalse.s loc_15441
0x1540b  ldloc.s  0x10
0x1540d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x15412  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Parse(string)
0x15417  stloc.s  0x13
0x15419  ldloc.s  0x13
0x1541b  ldstr    aSelectedenviro// "SelectedEnvironmentName"
0x15420  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x15425  brtrue.s loc_1542E
0x15427  ldsfld   string [mscorlib]System.String::Empty
0x1542c  br.s     loc_1543F
0x1542e  ldloc.s  0x13
0x15430  ldstr    aSelectedenviro// "SelectedEnvironmentName"
0x15435  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x1543a  callvirt instance string [mscorlib]System.Object::ToString()
0x1543f  stloc.s  0xF
0x15441  ldloc.s  0xE
0x15443  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x15448  call     bool [mscorlib]System.Convert::ToBoolean(string)
0x1544d  stloc.s  0x11
0x1544f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x15454  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MicrosoftFlowUtils::GetTenantId(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15459  stloc.s  0x12
0x1545b  call     class [Microsoft.Crm.Application.Pages]Microsoft.Crm.Web.Tools.MicrosoftFlow.FlowTelemetryEventSource [Microsoft.Crm.Application.Pages]Microsoft.Crm.Web.Tools.MicrosoftFlow.FlowTelemetryEventSource::get_Instance()
0x15460  ldloc.s  0x11
0x15462  ldloc.s  0x12
0x15464  ldloc.s  0xF
0x15466  callvirt instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Web.Tools.MicrosoftFlow.FlowTelemetryEventSource::LogMsFlowSettingsChanged(bool, string, string)
0x1546b  ldloc.s  0xD
0x1546d  ldloc.1
0x1546e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0x15473  ldloc.s  0xD
0x15475  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1547a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1547f  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x15484  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x15489  ldloc.s  0xD
0x1548b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x15490  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x15495  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1549a  ldc.i4.0
0x1549b  ldstr    a0_2// "{0}"
0x154a0  ldc.i4.1
0x154a1  newarr   [mscorlib]System.Object
0x154a6  dup
0x154a7  ldc.i4.0
0x154a8  ldstr    aUpdatedOrganiz// "Updated organization settings."
0x154ad  stelem.ref
0x154ae  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x154b3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.MasterSiteMapCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.MasterSiteMapCache::Instance()
0x154b8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x154bd  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<int32, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.MasterSiteMap>>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x154c2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x154c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x154cc  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x154d1  ldstr    a0_2// "{0}"
0x154d6  ldc.i4.1
0x154d7  newarr   [mscorlib]System.Object
0x154dc  dup
0x154dd  ldc.i4.0
0x154de  ldstr    aFlushingSitema// "Flushing SiteMap cache."
0x154e3  stelem.ref
0x154e4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x154e9  ldloc.s  0xD
0x154eb  ldstr    aPricingdecimal// "pricingdecimalprecision"
0x154f0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x154f5  brfalse.s loc_15554
0x154f7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x154fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x15501  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x15506  ldstr    a0_2// "{0}"
0x1550b  ldc.i4.1
0x1550c  newarr   [mscorlib]System.Object
0x15511  dup
0x15512  ldc.i4.0
0x15513  ldstr    aFlushingMetada// "Flushing Metadata cache."
0x15518  stelem.ref
0x15519  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1551e  ldc.i4   0x402
0x15523  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x15528  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1552d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x15532  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x15537  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x1553c  ldstr    a0_2// "{0}"
0x15541  ldc.i4.1
0x15542  newarr   [mscorlib]System.Object
0x15547  dup
0x15548  ldc.i4.0
0x15549  ldstr    aFlushedMetadat// "Flushed Metadata cache."
0x1554e  stelem.ref
0x1554f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x15554  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::.ctor()
0x15559  stloc.s  9
0x1555b  ldloc.2
0x1555c  ldstr    aOrganizationIs_0// "//organization/isauditenabled"
0x15561  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15566  stloc.s  0xA
0x15568  ldloc.2
0x15569  ldstr    aOrganizationIs_1// "//organization/isreadauditenabled"
0x1556e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15573  stloc.s  0xB
0x15575  ldloc.s  0xA
0x15577  brfalse.s loc_1559D
0x15579  ldloc.s  9
0x1557b  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::.ctor()
0x15580  dup
0x15581  ldstr    aIsauditenabled// "IsAuditEnabled"
0x15586  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Key(string)
0x1558b  dup
0x1558c  ldloc.s  0xA
0x1558e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x15593  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Value(string)
0x15598  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::Add(var<u1>)
0x1559d  ldloc.s  0xB
0x1559f  brfalse.s loc_155C5
0x155a1  ldloc.s  9
0x155a3  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::.ctor()
0x155a8  dup
0x155a9  ldstr    aIsreadauditena// "IsReadAuditEnabled"
0x155ae  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Key(string)
0x155b3  dup
0x155b4  ldloc.s  0xB
0x155b6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x155bb  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Value(string)
0x155c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::Add(var<u1>)
0x155c5  ldloc.s  9
0x155c7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::get_Count()
0x155cc  ldc.i4.0
0x155cd  ble.s    loc_1563D
0x155cf  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::.ctor()
0x155d4  stloc.s  0x14
0x155d6  ldloc.s  0x14
0x155d8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x155dd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x155e2  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_SystemUserId(valuetype [mscorlib]System.Guid)
0x155e7  ldloc.s  0x14
0x155e9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x155ee  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x155f3  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x155f8  ldloc.s  0x14
0x155fa  ldloc.s  9
0x155fc  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_Fields(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>)
0x15601  ldloc.s  0x14
  ... truncated ...
```
