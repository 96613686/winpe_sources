# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::ConfigureFormHandler

- ea: `0x1610`
- end: `0x179a`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::ConfigureFormHandler`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x15f0`
- `0x1600`
- `0x1610`

## string_xrefs

- `0x167b`: `istemplate`
- `0x16d7`: `istemplate`
- `0x1780`: `Object_Singular_CampaignTemplate`
- `0x1628`: `template`
- `0x1646`: `For this campaign IsTemplate = {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1610  ldarg.0
0x1611  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x1616  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm
0x161b  stloc.0
0x161c  ldarg.0
0x161d  ldarg.0
0x161e  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x1623  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1628  ldstr    aTemplate// "template"
0x162d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1632  call     instance void Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::set_IsTemplate(string value)
0x1637  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x163c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1641  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x1646  ldstr    aForThisCampaig// "For this campaign IsTemplate = {0}"
0x164b  ldc.i4.1
0x164c  newarr   [mscorlib]System.Object
0x1651  dup
0x1652  ldc.i4.0
0x1653  ldarg.0
0x1654  call     instance string Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::get_IsTemplate()
0x1659  stelem.ref
0x165a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x165f  ldarg.0
0x1660  call     instance string Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::get_IsTemplate()
0x1665  brfalse.s loc_16A0
0x1667  ldarg.0
0x1668  call     instance string Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::get_IsTemplate()
0x166d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1672  ldc.i4.0
0x1673  ble.s    loc_16A0
0x1675  ldarg.0
0x1676  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x167b  ldstr    aIstemplate// "istemplate"
0x1680  ldarg.0
0x1681  call     instance string Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::get_IsTemplate()
0x1686  ldstr    a1// "1"
0x168b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1690  brtrue.s loc_1695
0x1692  ldc.i4.0
0x1693  br.s     loc_1696
0x1695  ldc.i4.1
0x1696  box      [mscorlib]System.Boolean
0x169b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x16a0  ldloc.0
0x16a1  ldarg.0
0x16a2  ldftn    instance void Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::CustomFields_DataBoundReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0x16a8  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler::.ctor(object, native int)
0x16ad  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::add_DataBound(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler)
0x16b2  ldloc.0
0x16b3  ldarg.0
0x16b4  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x16b9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x16be  ldarg.0
0x16bf  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x16c4  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x16c9  ldc.i4.1
0x16ca  beq.s    loc_16FD
0x16cc  ldarg.0
0x16cd  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x16d2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x16d7  ldstr    aIstemplate// "istemplate"
0x16dc  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x16e1  stloc.1
0x16e2  ldloc.1
0x16e3  ldstr    a1// "1"
0x16e8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16ed  brfalse.s loc_16FD
0x16ef  ldarg.0
0x16f0  ldc.i4.1
0x16f1  stfld    bool Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::TemplateTitle
0x16f6  ldarg.0
0x16f7  ldloc.1
0x16f8  call     instance void Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::set_IsTemplate(string value)
0x16fd  ldarg.0
0x16fe  ldfld    bool Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::TemplateTitle
0x1703  brfalse  loc_1799
0x1708  ldarg.0
0x1709  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x170e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x1713  brfalse.s loc_1728
0x1715  ldarg.0
0x1716  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x171b  ldstr    aFormTitleNew// "Form_Title_New"
0x1720  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1725  stloc.2
0x1726  br.s     loc_1755
0x1728  ldarg.0
0x1729  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x172e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Title()
0x1733  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlDecode(string)
0x1738  stloc.2
0x1739  ldloc.2
0x173a  brfalse.s loc_1744
0x173c  ldloc.2
0x173d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1742  brtrue.s loc_1755
0x1744  ldarg.0
0x1745  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x174a  ldstr    aFormTitleUnkno// "Form_Title_Unknown"
0x174f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1754  stloc.2
0x1755  ldarg.0
0x1756  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x175b  ldstr    aFormTitleMask// "Form_Title_Mask"
0x1760  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1765  stloc.3
0x1766  ldarg.0
0x1767  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x176c  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1771  ldloc.3
0x1772  ldc.i4.2
0x1773  newarr   [mscorlib]System.Object
0x1778  dup
0x1779  ldc.i4.0
0x177a  ldarg.0
0x177b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x1780  ldstr    aObjectSingular// "Object_Singular_CampaignTemplate"
0x1785  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x178a  stelem.ref
0x178b  dup
0x178c  ldc.i4.1
0x178d  ldloc.2
0x178e  stelem.ref
0x178f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1794  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x1799  ret
```
