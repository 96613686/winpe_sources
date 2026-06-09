# Microsoft.Crm.Web.Tools.Solution.UninstallDialogPage::ConfigureForm

- ea: `0x55200`
- end: `0x55332`
- name: `Microsoft.Crm.Web.Tools.Solution.UninstallDialogPage::ConfigureForm`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x55200`

## string_xrefs

- `0x55251`: `Dialog_Delete_Title`
- `0x5527b`: `Dialog_Delete_Description`
- `0x552e8`: `Solution.Messages.ConfirmDelete.Managed.Title`
- `0x552fe`: `Solution.Messages.ConfirmDelete.Managed`
- `0x55316`: `Solution.Messages.ConfirmDelete.UnManaged`

## pseudocode

```c

```

## disassembly

```asm
0x55200  ldarg.0
0x55201  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x55206  ldarg.0
0x55207  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5520c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x55211  ldstr    aId// "id"
0x55216  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5521b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x55220  brfalse.s loc_5522D
0x55222  ldstr    aInvalidSolutio// "Invalid solution id."
0x55227  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5522c  throw
0x5522d  ldarg.0
0x5522e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x55233  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x55238  stloc.0
0x55239  ldc.i4   0x1BBC
0x5523e  ldc.i4.1
0x5523f  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x55244  stloc.1
0x55245  ldloc.0
0x55246  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x5524b  ldarg.0
0x5524c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x55251  ldstr    aDialogDeleteTi// "Dialog_Delete_Title"
0x55256  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5525b  ldc.i4.1
0x5525c  newarr   [mscorlib]System.Object
0x55261  dup
0x55262  ldc.i4.0
0x55263  ldloc.1
0x55264  stelem.ref
0x55265  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5526a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x5526f  ldloc.0
0x55270  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x55275  ldarg.0
0x55276  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5527b  ldstr    aDialogDeleteDe// "Dialog_Delete_Description"
0x55280  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x55285  ldc.i4.1
0x55286  newarr   [mscorlib]System.Object
0x5528b  dup
0x5528c  ldc.i4.0
0x5528d  ldloc.1
0x5528e  stelem.ref
0x5528f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x55294  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x55299  ldstr    aSolution// "solution"
0x5529e  ldarg.0
0x5529f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x552a4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x552a9  ldstr    aId// "id"
0x552ae  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x552b3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x552b8  ldc.i4.1
0x552b9  newarr   [mscorlib]System.String
0x552be  dup
0x552bf  ldc.i4.0
0x552c0  ldstr    aIsmanaged// "ismanaged"
0x552c5  stelem.ref
0x552c6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x552cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x552d0  ldstr    aIsmanaged// "ismanaged"
0x552d5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x552da  unbox.any [mscorlib]System.Boolean
0x552df  brfalse.s loc_5530F
0x552e1  ldloc.0
0x552e2  ldarg.0
0x552e3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x552e8  ldstr    aSolutionMessag// "Solution.Messages.ConfirmDelete.Managed"...
0x552ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x552f2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x552f7  ldarg.0
0x552f8  ldarg.0
0x552f9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x552fe  ldstr    aSolutionMessag_0// "Solution.Messages.ConfirmDelete.Managed"
0x55303  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x55308  stfld    string Microsoft.Crm.Web.Tools.Solution.UninstallDialogPage::BodyDescription
0x5530d  br.s     loc_55325
0x5530f  ldarg.0
0x55310  ldarg.0
0x55311  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x55316  ldstr    aSolutionMessag_1// "Solution.Messages.ConfirmDelete.UnManag"...
0x5531b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x55320  stfld    string Microsoft.Crm.Web.Tools.Solution.UninstallDialogPage::BodyDescription
0x55325  ldarg.0
0x55326  ldloc.0
0x55327  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::get_DialogTitle()
0x5532c  stfld    string Microsoft.Crm.Web.Tools.Solution.UninstallDialogPage::SpinCaption
0x55331  ret
```
