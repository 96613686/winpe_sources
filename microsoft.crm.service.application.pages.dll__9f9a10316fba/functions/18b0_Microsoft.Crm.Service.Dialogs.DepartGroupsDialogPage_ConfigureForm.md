# Microsoft.Crm.Service.Dialogs.DepartGroupsDialogPage::ConfigureForm

- ea: `0x18b0`
- end: `0x1a11`
- name: `Microsoft.Crm.Service.Dialogs.DepartGroupsDialogPage::ConfigureForm`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18b0`

## pseudocode

```c

```

## disassembly

```asm
0x18b0  ldarg.0
0x18b1  ldarg.0
0x18b2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18b7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x18bc  ldstr    aItotal// "iTotal"
0x18c1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18c6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18cb  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x18d0  stfld    int32 Microsoft.Crm.Service.Dialogs.DepartGroupsDialogPage::total
0x18d5  ldarg.0
0x18d6  ldc.i4   0xFA7
0x18db  stfld    int32 Microsoft.Crm.Service.Dialogs.DepartGroupsDialogPage::objType
0x18e0  ldarg.0
0x18e1  ldfld    int32 Microsoft.Crm.Service.Dialogs.DepartGroupsDialogPage::objType
0x18e6  ldarg.0
0x18e7  ldfld    int32 Microsoft.Crm.Service.Dialogs.DepartGroupsDialogPage::total
0x18ec  ldc.i4.1
0x18ed  bgt.s    loc_18F2
0x18ef  ldc.i4.1
0x18f0  br.s     loc_18F3
0x18f2  ldc.i4.2
0x18f3  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x18f8  stloc.0
0x18f9  ldarg.0
0x18fa  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18ff  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1904  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1909  ldc.i4.0
0x190a  conv.i8
0x190b  ble      loc_199A
0x1910  ldloca.s 2
0x1912  ldarg.0
0x1913  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1918  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x191d  ldstr    aIid// "iId"
0x1922  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1927  call     instance void [mscorlib]System.Guid::.ctor(string)
0x192c  ldc.i4.1
0x192d  newarr   [mscorlib]System.Guid
0x1932  stloc.3
0x1933  ldloc.3
0x1934  ldc.i4.0
0x1935  ldarg.0
0x1936  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x193b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1940  ldstr    aTargetid// "targetid"
0x1945  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x194a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x194f  stelem   [mscorlib]System.Guid
0x1954  ldstr    aConstraintbase// "constraintbasedgroup"
0x1959  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x195e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1963  newobj   instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ConstraintBasedGroup::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1968  dup
0x1969  ldloc.2
0x196a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x196f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x1974  dup
0x1975  ldc.i4.0
0x1976  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_IsNew(bool)
0x197b  dup
0x197c  ldloc.3
0x197d  callvirt instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ConstraintBasedGroup::RemoveMembers(valuetype [mscorlib]System.Guid[])
0x1982  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x1987  ldarg.0
0x1988  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x198d  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x1992  leave.s  loc_199A
0x1994  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x1999  throw
0x199a  ldarg.0
0x199b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x19a0  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x19a5  stloc.1
0x19a6  ldloc.1
0x19a7  ldarg.0
0x19a8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x19ad  ldstr    aDialogDepartgr// "Dialog_DepartGroups_Title"
0x19b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19b7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x19bc  ldloc.1
0x19bd  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x19c2  ldarg.0
0x19c3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x19c8  ldstr    aDialogDepartgr_0// "Dialog_DepartGroups_Description"
0x19cd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19d2  ldc.i4.2
0x19d3  newarr   [mscorlib]System.Object
0x19d8  dup
0x19d9  ldc.i4.0
0x19da  ldarg.0
0x19db  ldfld    int32 Microsoft.Crm.Service.Dialogs.DepartGroupsDialogPage::total
0x19e0  box      [mscorlib]System.Int32
0x19e5  stelem.ref
0x19e6  dup
0x19e7  ldc.i4.1
0x19e8  ldloc.0
0x19e9  ldarg.0
0x19ea  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x19ef  ldstr    aDialogDepartgr_1// "Dialog_DepartGroups_Description_Casing"
0x19f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19f9  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCasedDisplayText(string, string)
0x19fe  stelem.ref
0x19ff  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1a04  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x1a09  ldloc.1
0x1a0a  ldc.i4.3
0x1a0b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x1a10  ret
```
