# Microsoft.Crm.Service.Application.Pages.Dialogs.CaseHierarchyDialog::ConfigureForm

- ea: `0x10710`
- end: `0x10ae6`
- name: `Microsoft.Crm.Service.Application.Pages.Dialogs.CaseHierarchyDialog::ConfigureForm`
- size: `982`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x10710`

## string_xrefs

- `0x107d4`: `text/xml`
- `0x107ec`: `/AttributeMaps/DeleteAttributeMaps/attributemap`
- `0x10877`: `/AttributeMaps/CreateAttributeMaps/attributemap`
- `0x10967`: `cascadestatusupdate`
- `0x10a0d`: `cascadestatusupdate`
- `0x10a33`: `cascadestatusupdate`
- `0x10a40`: `cascadestatusupdate`
- `0x10979`: `restrictstatusupdate`
- `0x10a15`: `restrictstatusupdate`
- `0x10a5e`: `restrictstatusupdate`
- `0x10a6b`: `restrictstatusupdate`

## pseudocode

```c

```

## disassembly

```asm
0x10710  ldarg.0
0x10711  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x10716  ldarg.0
0x10717  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1071c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x10721  dup
0x10722  ldc.i4.1
0x10723  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ShowStatusBar(bool)
0x10728  dup
0x10729  ldarg.0
0x1072a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1072f  ldstr    aWebGridCmdsDlg_6// "Web._grid.cmds.dlg_casehierarchy.aspx_1"
0x10734  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10739  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1073e  dup
0x1073f  ldarg.0
0x10740  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10745  ldstr    aWebGridCmdsDlg_7// "Web._grid.cmds.dlg_casehierarchy.aspx_2"
0x1074a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1074f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x10754  ldc.i4.s 0x23
0x10756  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x1075b  ldarg.0
0x1075c  ldstr    aOrganization// "organization"
0x10761  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10766  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1076b  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Service.Application.Pages.Dialogs.CaseHierarchyDialog::_entityType
0x10770  ldarg.0
0x10771  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Service.Application.Pages.Dialogs.CaseHierarchyDialog::_entityType
0x10776  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1077b  stloc.0
0x1077c  ldloc.0
0x1077d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationId()
0x10782  stloc.1
0x10783  ldloca.s 1
0x10785  constrained. [mscorlib]System.Guid
0x1078b  callvirt instance string [mscorlib]System.Object::ToString()
0x10790  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x10795  ldarg.0
0x10796  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1079b  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x107a0  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x107a5  ldc.i4.0
0x107a6  conv.i8
0x107a7  ble      loc_10A05
0x107ac  ldarg.0
0x107ad  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x107b2  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x107b7  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x107bc  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x107c1  stloc.2
0x107c2  ldloc.2
0x107c3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x107c8  ldc.i4.0
0x107c9  ble      loc_10AE5
0x107ce  ldarg.0
0x107cf  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x107d4  ldstr    aTextXml// "text/xml"
0x107d9  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x107de  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x107e3  stloc.3
0x107e4  ldloc.2
0x107e5  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x107ea  stloc.3
0x107eb  ldloc.3
0x107ec  ldstr    aAttributemapsD// "/AttributeMaps/DeleteAttributeMaps/attr"...
0x107f1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x107f6  stloc.s  4
0x107f8  ldloc.s  4
0x107fa  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x107ff  stloc.s  5
0x10801  br.s     loc_10848
0x10803  ldloc.s  5
0x10805  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1080a  castclass [System.Xml]System.Xml.XmlNode
0x1080f  stloc.s  6
0x10811  ldloc.s  6
0x10813  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x10818  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1081d  ldc.i4.0
0x1081e  ble.s    loc_10848
0x10820  newobj   instance void [Microsoft.Crm.Application.Components.WebServices.SystemCustomization]Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::.ctor()
0x10825  stloc.s  7
0x10827  ldloc.s  7
0x10829  ldloc.s  6
0x1082b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x10830  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x10835  callvirt instance void [Microsoft.Crm.Application.Components.WebServices.SystemCustomization]Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteAttributeMap(valuetype [mscorlib]System.Guid)
0x1083a  leave.s  loc_10848
0x1083c  ldloc.s  7
0x1083e  brfalse.s loc_10847
0x10840  ldloc.s  7
0x10842  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10847  endfinally
0x10848  ldloc.s  5
0x1084a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1084f  brtrue.s loc_10803
0x10851  leave.s  loc_10868
0x10853  ldloc.s  5
0x10855  isinst   [mscorlib]System.IDisposable
0x1085a  stloc.s  8
0x1085c  ldloc.s  8
0x1085e  brfalse.s loc_10867
0x10860  ldloc.s  8
0x10862  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10867  endfinally
0x10868  leave.s  loc_10876
0x1086a  ldloc.s  4
0x1086c  brfalse.s loc_10875
0x1086e  ldloc.s  4
0x10870  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10875  endfinally
0x10876  ldloc.3
0x10877  ldstr    aAttributemapsC// "/AttributeMaps/CreateAttributeMaps/attr"...
0x1087c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x10881  stloc.s  9
0x10883  ldloc.s  9
0x10885  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1088a  stloc.s  5
0x1088c  br.s     loc_108BA
0x1088e  ldloc.s  5
0x10890  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x10895  castclass [System.Xml]System.Xml.XmlNode
0x1089a  stloc.s  0xA
0x1089c  newobj   instance void [Microsoft.Crm.Application.Components.WebServices.SystemCustomization]Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::.ctor()
0x108a1  stloc.s  0xB
0x108a3  ldloc.s  0xB
0x108a5  ldloc.s  0xA
0x108a7  callvirt instance void [Microsoft.Crm.Application.Components.WebServices.SystemCustomization]Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateAttributeMap(class [System.Xml]System.Xml.XmlNode)
0x108ac  leave.s  loc_108BA
0x108ae  ldloc.s  0xB
0x108b0  brfalse.s loc_108B9
0x108b2  ldloc.s  0xB
0x108b4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x108b9  endfinally
0x108ba  ldloc.s  5
0x108bc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x108c1  brtrue.s loc_1088E
0x108c3  leave.s  loc_108DA
0x108c5  ldloc.s  5
0x108c7  isinst   [mscorlib]System.IDisposable
0x108cc  stloc.s  8
0x108ce  ldloc.s  8
0x108d0  brfalse.s loc_108D9
0x108d2  ldloc.s  8
0x108d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x108d9  endfinally
0x108da  leave.s  loc_108E8
0x108dc  ldloc.s  9
0x108de  brfalse.s loc_108E7
0x108e0  ldloc.s  9
0x108e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x108e7  endfinally
0x108e8  ldloc.3
0x108e9  ldstr    aAttributemapsO// "/AttributeMaps/OrgCascadeStatusAttribut"...
0x108ee  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x108f3  stloc.s  0xC
0x108f5  ldc.i4.0
0x108f6  stloc.s  0xD
0x108f8  ldc.i4.0
0x108f9  stloc.s  0xF
0x108fb  ldc.i4.0
0x108fc  stloc.s  0x10
0x108fe  ldloc.s  0xC
0x10900  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x10905  ldc.i4.2
0x10906  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1090b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x10910  ldloca.s 0x10
0x10912  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x10917  stloc.s  0xD
0x10919  ldloc.s  0xD
0x1091b  brfalse.s loc_1092C
0x1091d  ldloc.s  0x10
0x1091f  brtrue.s loc_1092C
0x10921  ldc.i4.0
0x10922  stloc.s  0xE
0x10924  ldc.i4.0
0x10925  stloc.s  0xF
0x10927  ldc.i4.1
0x10928  stloc.s  0xD
0x1092a  br.s     loc_10962
0x1092c  ldloc.s  0xC
0x1092e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x10933  ldc.i4.0
0x10934  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x10939  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1093e  ldloca.s 0xE
0x10940  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x10945  stloc.s  0xD
0x10947  ldloc.s  0xC
0x10949  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1094e  ldc.i4.1
0x1094f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x10954  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x10959  ldloca.s 0xF
0x1095b  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x10960  stloc.s  0xD
0x10962  ldloc.s  0xD
0x10964  brfalse.s loc_109AB
0x10966  ldloc.0
0x10967  ldstr    aCascadestatusu// "cascadestatusupdate"
0x1096c  ldloc.s  0xE
0x1096e  box      [mscorlib]System.Boolean
0x10973  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x10978  ldloc.0
0x10979  ldstr    aRestrictstatus// "restrictstatusupdate"
0x1097e  ldloc.s  0xF
0x10980  box      [mscorlib]System.Boolean
0x10985  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1098a  ldloc.0
0x1098b  ldc.i4.0
0x1098c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_RetrieveLatest(bool)
0x10991  ldloc.0
0x10992  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x10997  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x1099c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationId()
0x109a1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x109a6  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x109ab  leave.s  loc_109DE
0x109ad  stloc.s  0x11
0x109af  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x109b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x109b9  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x109be  ldstr    a0_0// "{0}"
0x109c3  ldc.i4.1
0x109c4  newarr   [mscorlib]System.Object
0x109c9  dup
0x109ca  ldc.i4.0
0x109cb  ldstr    aErrorOccuredWh// "Error occured while updating the case h"...
0x109d0  stelem.ref
0x109d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x109d6  ldloc.s  0x11
0x109d8  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x109dd  throw
0x109de  ldarg.0
0x109df  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x109e4  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x109e9  ldarg.0
0x109ea  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x109ef  ldstr    aOk// "<ok/>"
0x109f4  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x109f9  ldarg.0
0x109fa  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x109ff  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x10a04  ret
0x10a05  ldc.i4.2
0x10a06  newarr   [mscorlib]System.String
0x10a0b  dup
0x10a0c  ldc.i4.0
0x10a0d  ldstr    aCascadestatusu// "cascadestatusupdate"
0x10a12  stelem.ref
0x10a13  dup
0x10a14  ldc.i4.1
0x10a15  ldstr    aRestrictstatus// "restrictstatusupdate"
0x10a1a  stelem.ref
0x10a1b  stloc.s  0x12
0x10a1d  ldloc.0
0x10a1e  ldc.i4.0
0x10a1f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_RetrieveLatest(bool)
0x10a24  ldloc.0
0x10a25  ldloc.s  0x12
0x10a27  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string[])
0x10a2c  ldarg.0
0x10a2d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton Microsoft.Crm.Service.Application.Pages.Dialogs.CaseHierarchyDialog::rdChildCases
0x10a32  ldloc.0
0x10a33  ldstr    aCascadestatusu// "cascadestatusupdate"
0x10a38  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x10a3d  brfalse.s loc_10A51
0x10a3f  ldloc.0
0x10a40  ldstr    aCascadestatusu// "cascadestatusupdate"
0x10a45  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x10a4a  unbox.any [mscorlib]System.Boolean
0x10a4f  br.s     loc_10A52
0x10a51  ldc.i4.0
0x10a52  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton::set_Checked(bool)
0x10a57  ldarg.0
0x10a58  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton Microsoft.Crm.Service.Application.Pages.Dialogs.CaseHierarchyDialog::rdRestrict
0x10a5d  ldloc.0
0x10a5e  ldstr    aRestrictstatus// "restrictstatusupdate"
0x10a63  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x10a68  brfalse.s loc_10A7C
0x10a6a  ldloc.0
0x10a6b  ldstr    aRestrictstatus// "restrictstatusupdate"
0x10a70  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x10a75  unbox.any [mscorlib]System.Boolean
0x10a7a  br.s     loc_10A7D
0x10a7c  ldc.i4.0
0x10a7d  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton::set_Checked(bool)
0x10a82  ldarg.0
0x10a83  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton Microsoft.Crm.Service.Application.Pages.Dialogs.CaseHierarchyDialog::rdChildCases
0x10a88  callvirt instance bool [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton::get_Checked()
0x10a8d  brtrue.s loc_10AC1
0x10a8f  ldarg.0
0x10a90  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton Microsoft.Crm.Service.Application.Pages.Dialogs.CaseHierarchyDialog::rdRestrict
0x10a95  callvirt instance bool [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton::get_Checked()
0x10a9a  brtrue.s loc_10AC1
0x10a9c  ldarg.0
0x10a9d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Service.Application.Pages.Dialogs.CaseHierarchyDialog::checkBoxCaseCascade
0x10aa2  ldc.i4.0
  ... truncated ...
```
