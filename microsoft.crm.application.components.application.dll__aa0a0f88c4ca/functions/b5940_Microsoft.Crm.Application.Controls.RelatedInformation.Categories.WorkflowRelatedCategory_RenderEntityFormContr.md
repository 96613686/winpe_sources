# Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory::RenderEntityFormControls

- ea: `0xb5940`
- end: `0xb5b34`
- name: `Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory::RenderEntityFormControls`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xb5300`

## callees

- `0x19fe0`
- `0x242b0`
- `0x24430`
- `0xb5940`
- `0xb5b40`
- `0xb6150`

## string_xrefs

- `0xb59c4`: `/_imgs/ico_16_delete.gif`
- `0xb59f9`: `/_imgs/picklist/cmd_moveup.png`
- `0xb5a3d`: `/_imgs/picklist/cmd_movedown.png`
- `0xb59aa`: `RemoveFromDynamicValueList();`
- `0xb59df`: `MoveDynamicValueUp();`
- `0xb5a23`: `MoveDynamicValueDown();`

## pseudocode

```c

```

## disassembly

```asm
0xb5940  ldarg.1
0xb5941  ldstr    aTableWidth100C_6// "<table width=\"100%\" cellpadding=\"0\""...
0xb5946  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb594b  ldarg.0
0xb594c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb5951  ldstr    aWorkflowDynami_4// "Workflow.DynamicExpressions.Add"
0xb5956  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb595b  ldstr    aAddtodynamicva// "AddToDynamicValueList()"
0xb5960  ldstr    aWfdynamicexpre// "wfDynamicExpressionAdd"
0xb5965  ldarg.1
0xb5966  call     instance void Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory::RenderButton(string label, string onClickEventHandler, string id, class [System.Web]System.Web.UI.HtmlTextWriter output)
0xb596b  ldarg.1
0xb596c  ldstr    aTdTrTable// "</td></tr></table>"
0xb5971  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb5976  newobj   instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::.ctor()
0xb597b  stloc.0
0xb597c  ldloc.0
0xb597d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0xb5982  ldc.i4.0
0xb5983  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool)
0xb5988  ldloc.0
0xb5989  ldc.i4.0
0xb598a  callvirt instance void Microsoft.Crm.Application.Menus.AppMenuBar::Execute(bool showToolBar)
0xb598f  ldloc.0
0xb5990  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0xb5995  ldstr    aMsCrmGridactio// "ms-crm-GridActionBar"
0xb599a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0xb599f  ldloc.0
0xb59a0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0xb59a5  ldsfld   string [mscorlib]System.String::Empty
0xb59aa  ldstr    aRemovefromdyna// "RemoveFromDynamicValueList();"
0xb59af  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xb59b4  ldc.i4.1
0xb59b5  newarr   [mscorlib]System.Char
0xb59ba  dup
0xb59bb  ldc.i4.0
0xb59bc  ldc.i4.s 0x2F
0xb59be  stelem.i2
0xb59bf  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xb59c4  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0xb59c9  call     string [mscorlib]System.String::Concat(string, string)
0xb59ce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string)
0xb59d3  pop
0xb59d4  ldloc.0
0xb59d5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0xb59da  ldsfld   string [mscorlib]System.String::Empty
0xb59df  ldstr    aMovedynamicval// "MoveDynamicValueUp();"
0xb59e4  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xb59e9  ldc.i4.1
0xb59ea  newarr   [mscorlib]System.Char
0xb59ef  dup
0xb59f0  ldc.i4.0
0xb59f1  ldc.i4.s 0x2F
0xb59f3  stelem.i2
0xb59f4  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xb59f9  ldstr    aImgsPicklistCm_0// "/_imgs/picklist/cmd_moveup.png"
0xb59fe  call     string [mscorlib]System.String::Concat(string, string)
0xb5a03  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb5a08  ldstr    aWorkflowDynami_5// "Workflow.DynamicExpressions.Up"
0xb5a0d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5a12  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0xb5a17  pop
0xb5a18  ldloc.0
0xb5a19  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0xb5a1e  ldsfld   string [mscorlib]System.String::Empty
0xb5a23  ldstr    aMovedynamicval_0// "MoveDynamicValueDown();"
0xb5a28  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xb5a2d  ldc.i4.1
0xb5a2e  newarr   [mscorlib]System.Char
0xb5a33  dup
0xb5a34  ldc.i4.0
0xb5a35  ldc.i4.s 0x2F
0xb5a37  stelem.i2
0xb5a38  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xb5a3d  ldstr    aImgsPicklistCm_1// "/_imgs/picklist/cmd_movedown.png"
0xb5a42  call     string [mscorlib]System.String::Concat(string, string)
0xb5a47  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb5a4c  ldstr    aWorkflowDynami_6// "Workflow.DynamicExpressions.Down"
0xb5a51  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5a56  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0xb5a5b  pop
0xb5a5c  ldloc.0
0xb5a5d  ldarg.1
0xb5a5e  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0xb5a63  ldarg.0
0xb5a64  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory::GetNewSelectControl()
0xb5a69  stloc.1
0xb5a6a  ldloc.1
0xb5a6b  ldstr    aDynamicvaluese// "dynamicValueSelector"
0xb5a70  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xb5a75  ldloc.1
0xb5a76  ldstr    aSize_0// "SIZE"
0xb5a7b  ldstr    a5_0// "5"
0xb5a80  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddExpando(string, string)
0xb5a85  ldloc.1
0xb5a86  ldarg.1
0xb5a87  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0xb5a8c  ldarg.1
0xb5a8d  ldloc.1
0xb5a8e  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_ClientSideFormInputBehaviorClassName()
0xb5a93  ldloc.1
0xb5a94  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xb5a99  call     void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.SharedMethods::RenderClientControlRegistrationScript(class [mscorlib]System.IO.TextWriter, string, string)
0xb5a9e  ldarg.1
0xb5a9f  ldstr    aTableWidth100C_7// "<table width=\"100%\" cellpadding=\"0\""...
0xb5aa4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb5aa9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb5aae  ldstr    aWorkflowDynami_7// "Workflow.DynamicExpressions.DefaultValu"...
0xb5ab3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5ab8  ldarg.1
0xb5ab9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0xb5abe  ldarg.1
0xb5abf  ldstr    aSpanNbspTdTr// "</span>&nbsp;</td></tr>"
0xb5ac4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb5ac9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xb5ace  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xb5ad3  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0xb5ad8  brfalse.s loc_B5AE7
0xb5ada  ldarg.1
0xb5adb  ldstr    aTrTdValignTopN_0// "<tr><td valign=\"top\">&nbsp;<span id="...
0xb5ae0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb5ae5  br.s     loc_B5AF2
0xb5ae7  ldarg.1
0xb5ae8  ldstr    aTrTdValignTopS// "<tr><td valign=\"top\"><span id=\"defau"...
0xb5aed  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb5af2  ldarg.1
0xb5af3  ldstr    aTable// "</table>"
0xb5af8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb5afd  ldarg.1
0xb5afe  ldstr    aTableWidth100C_8// "<table width=\"100%\" cellpadding=\"0\""...
0xb5b03  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb5b08  ldarg.0
0xb5b09  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb5b0e  ldstr    aWorkflowDynami_8// "Workflow.DynamicExpressions.Ok"
0xb5b13  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5b18  ldstr    aInsertslug// "InsertSlug()"
0xb5b1d  ldstr    aWfdynamicexpre_0// "wfDynamicExpressionOk"
0xb5b22  ldarg.1
0xb5b23  call     instance void Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory::RenderButton(string label, string onClickEventHandler, string id, class [System.Web]System.Web.UI.HtmlTextWriter output)
0xb5b28  ldarg.1
0xb5b29  ldstr    aTdTrTable// "</td></tr></table>"
0xb5b2e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb5b33  ret
```
