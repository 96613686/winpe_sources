# Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderOutlookAppGrid::AddDetailLinkControl

- ea: `0xd4cc0`
- end: `0xd4f50`
- name: `Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderOutlookAppGrid::AddDetailLinkControl`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xd4430`

## callees

- `0xd4cc0`

## string_xrefs

- `0xd4cd1`: `ms-crm-CrmAppForOutlook-editLink`
- `0xd4d7d`: `(new Mscrm.AppsForCrm.AppsForCrmAdminSettings()).OpenInstallStatusDetailsDialog('`
- `0xd4e54`: `(new Mscrm.AppsForCrm.AppsForCrmAdminSettings()).OpenInstallStatusDetailsDialog('`

## pseudocode

```c

```

## disassembly

```asm
0xd4cc0  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::.ctor()
0xd4cc5  stloc.0
0xd4cc6  ldloc.0
0xd4cc7  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd4ccc  ldstr    aClass_3// "CLASS"
0xd4cd1  ldstr    aMsCrmCrmappfor// "ms-crm-CrmAppForOutlook-editLink"
0xd4cd6  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd4cdb  ldloc.0
0xd4cdc  ldstr    aJavascriptVoid_2// "javascript:void(0)"
0xd4ce1  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0xd4ce6  ldloc.0
0xd4ce7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd4cec  ldstr    aGriddataurl0// "gridDataURL_{0}"
0xd4cf1  ldc.i4.1
0xd4cf2  newarr   [mscorlib]System.Object
0xd4cf7  dup
0xd4cf8  ldc.i4.0
0xd4cf9  ldarg.2
0xd4cfa  box      [mscorlib]System.Guid
0xd4cff  stelem.ref
0xd4d00  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd4d05  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xd4d0a  ldloc.0
0xd4d0b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd4d10  ldstr    aMailappGeneric// "MailApp.Generic.LearnMore"
0xd4d15  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4d1a  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_Title(string)
0xd4d1f  ldloc.0
0xd4d20  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd4d25  ldstr    aMailappGeneric// "MailApp.Generic.LearnMore"
0xd4d2a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4d2f  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xd4d34  ldarg.1
0xd4d35  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd4d3a  ldc.i4.2
0xd4d3b  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCell [System.Web]System.Web.UI.WebControls.TableCellCollection::get_Item(int32)
0xd4d40  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4d45  ldstr    aNobrClassGridc_1// "<nobr class='gridcellpadding'>"
0xd4d4a  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0xd4d4f  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd4d54  ldarg.s  4
0xd4d56  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd4d5b  brtrue   loc_D4E26
0xd4d60  ldarg.s  4
0xd4d62  ldarg.0
0xd4d63  ldfld    string Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderOutlookAppGrid::officeAppsDeploymentScheduled
0xd4d68  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd4d6d  brfalse  loc_D4E26
0xd4d72  ldloc.0
0xd4d73  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd4d78  ldstr    aOnclick// "onclick"
0xd4d7d  ldstr    aNewMscrmAppsfo// "(new Mscrm.AppsForCrm.AppsForCrmAdminSe"...
0xd4d82  ldarga.s 2
0xd4d84  constrained. [mscorlib]System.Guid
0xd4d8a  callvirt instance string [mscorlib]System.Object::ToString()
0xd4d8f  ldstr    aTrue_2// "', 'true');"
0xd4d94  call     string [mscorlib]System.String::Concat(string, string, string)
0xd4d99  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd4d9e  ldarg.1
0xd4d9f  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd4da4  ldc.i4.2
0xd4da5  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCell [System.Web]System.Web.UI.WebControls.TableCellCollection::get_Item(int32)
0xd4daa  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4daf  ldstr    aSpanTabindex0S_2// "<span tabindex='0' style='color:#ff7f00"...
0xd4db4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd4db9  ldstr    aMailappRootpag_7// "MailApp.RootPage.Grid.Column.Status.Val"...
0xd4dbe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4dc3  ldstr    asc_1AA360// "'>"
0xd4dc8  call     string [mscorlib]System.String::Concat(string, string, string)
0xd4dcd  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0xd4dd2  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd4dd7  ldarg.1
0xd4dd8  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd4ddd  ldc.i4.2
0xd4dde  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCell [System.Web]System.Web.UI.WebControls.TableCellCollection::get_Item(int32)
0xd4de3  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4de8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd4ded  ldstr    aMailappRootpag_7// "MailApp.RootPage.Grid.Column.Status.Val"...
0xd4df2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4df7  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0xd4dfc  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd4e01  ldarg.1
0xd4e02  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd4e07  ldc.i4.2
0xd4e08  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCell [System.Web]System.Web.UI.WebControls.TableCellCollection::get_Item(int32)
0xd4e0d  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4e12  ldstr    aSpan// "</span>"
0xd4e17  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0xd4e1c  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd4e21  br       loc_D4EF8
0xd4e26  ldarg.3
0xd4e27  ldarg.0
0xd4e28  ldfld    string[] Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderOutlookAppGrid::officeAppsDeploymentStatusOptions
0xd4e2d  ldc.i4.2
0xd4e2e  ldelem.ref
0xd4e2f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd4e34  brtrue.s loc_D4E49
0xd4e36  ldarg.3
0xd4e37  ldarg.0
0xd4e38  ldfld    string[] Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderOutlookAppGrid::officeAppsDeploymentStatusOptions
0xd4e3d  ldc.i4.3
0xd4e3e  ldelem.ref
0xd4e3f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd4e44  brfalse  loc_D4EF8
0xd4e49  ldloc.0
0xd4e4a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd4e4f  ldstr    aOnclick// "onclick"
0xd4e54  ldstr    aNewMscrmAppsfo// "(new Mscrm.AppsForCrm.AppsForCrmAdminSe"...
0xd4e59  ldarga.s 2
0xd4e5b  constrained. [mscorlib]System.Guid
0xd4e61  callvirt instance string [mscorlib]System.Object::ToString()
0xd4e66  ldstr    aFalse_1// "', 'false');"
0xd4e6b  call     string [mscorlib]System.String::Concat(string, string, string)
0xd4e70  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd4e75  ldarg.1
0xd4e76  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd4e7b  ldc.i4.2
0xd4e7c  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCell [System.Web]System.Web.UI.WebControls.TableCellCollection::get_Item(int32)
0xd4e81  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4e86  ldstr    aSpanTabindex0S_3// "<span tabindex='0' style='color:#d20000"...
0xd4e8b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd4e90  ldstr    aMailappRootpag_8// "MailApp.RootPage.Grid.Column.Status.Val"...
0xd4e95  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4e9a  ldstr    asc_1AA360// "'>"
0xd4e9f  call     string [mscorlib]System.String::Concat(string, string, string)
0xd4ea4  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0xd4ea9  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd4eae  ldarg.1
0xd4eaf  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd4eb4  ldc.i4.2
0xd4eb5  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCell [System.Web]System.Web.UI.WebControls.TableCellCollection::get_Item(int32)
0xd4eba  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4ebf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd4ec4  ldstr    aMailappRootpag_8// "MailApp.RootPage.Grid.Column.Status.Val"...
0xd4ec9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4ece  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0xd4ed3  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd4ed8  ldarg.1
0xd4ed9  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd4ede  ldc.i4.2
0xd4edf  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCell [System.Web]System.Web.UI.WebControls.TableCellCollection::get_Item(int32)
0xd4ee4  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4ee9  ldstr    aSpan// "</span>"
0xd4eee  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0xd4ef3  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd4ef8  ldarg.1
0xd4ef9  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd4efe  ldc.i4.2
0xd4eff  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCell [System.Web]System.Web.UI.WebControls.TableCellCollection::get_Item(int32)
0xd4f04  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4f09  ldstr    aNbsp_4// "&nbsp"
0xd4f0e  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0xd4f13  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd4f18  ldarg.1
0xd4f19  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd4f1e  ldc.i4.2
0xd4f1f  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCell [System.Web]System.Web.UI.WebControls.TableCellCollection::get_Item(int32)
0xd4f24  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4f29  ldloc.0
0xd4f2a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd4f2f  ldarg.1
0xd4f30  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd4f35  ldc.i4.2
0xd4f36  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCell [System.Web]System.Web.UI.WebControls.TableCellCollection::get_Item(int32)
0xd4f3b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4f40  ldstr    aNobr_0// "</nobr>"
0xd4f45  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0xd4f4a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd4f4f  ret
```
