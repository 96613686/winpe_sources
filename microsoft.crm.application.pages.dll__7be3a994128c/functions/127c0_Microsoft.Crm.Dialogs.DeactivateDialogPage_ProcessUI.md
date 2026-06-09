# Microsoft.Crm.Dialogs.DeactivateDialogPage::ProcessUI

- ea: `0x127c0`
- end: `0x136f4`
- name: `Microsoft.Crm.Dialogs.DeactivateDialogPage::ProcessUI`
- size: `3892`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x11fc0`

## callees

- `0x127c0`
- `0x13700`
- `0x13830`
- `0x13860`
- `0x13870`

## string_xrefs

- `0x12e5d`: `Dialog_Deactivate_For_ChannelAccessProfileRule`
- `0x12f0d`: `Dialog_Deactivate_ChannelAccessProfile_Title`
- `0x12f31`: `Dialog_Deactivate_Multiple_ChannelAccessProfile_Description`
- `0x12f5d`: `Dialog_Deactivate_Single_ChannelAccessProfile_Description`

## pseudocode

```c

```

## disassembly

```asm
0x127c0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x127c5  stloc.0
0x127c6  ldarg.0
0x127c7  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Dialogs.DeactivateDialogPage::entityType
0x127cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x127d1  stloc.1
0x127d2  ldarg.0
0x127d3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x127d8  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x127dd  stloc.2
0x127de  ldarg.0
0x127df  ldfld    int32 Microsoft.Crm.Dialogs.DeactivateDialogPage::iTotal
0x127e4  ldc.i4.1
0x127e5  bgt.s    loc_127EA
0x127e7  ldc.i4.1
0x127e8  br.s     loc_127EB
0x127ea  ldc.i4.2
0x127eb  stloc.3
0x127ec  ldarg.0
0x127ed  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Dialogs.DeactivateDialogPage::WarningMessageDiv
0x127f2  ldc.i4.0
0x127f3  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x127f8  ldarg.0
0x127f9  ldfld    int32 Microsoft.Crm.Dialogs.DeactivateDialogPage::ObjType
0x127fe  stloc.s  5
0x12800  ldloc.s  5
0x12802  ldc.i4   0xBBD
0x12807  bgt.s    loc_12851
0x12809  ldloc.s  5
0x1280b  ldc.i4.8
0x1280c  bgt.s    loc_1282B
0x1280e  ldloc.s  5
0x12810  ldc.i4.1
0x12811  beq      loc_129E6
0x12816  ldloc.s  5
0x12818  ldc.i4.2
0x12819  beq      loc_129E6
0x1281e  ldloc.s  5
0x12820  ldc.i4.8
0x12821  beq      loc_12ACA
0x12826  br       loc_13017
0x1282b  ldloc.s  5
0x1282d  ldc.i4.s 0xA
0x1282f  beq      loc_128C6
0x12834  ldloc.s  5
0x12836  ldc.i4   0x438
0x1283b  beq      loc_12956
0x12840  ldloc.s  5
0x12842  ldc.i4   0xBBD
0x12847  beq      loc_12EEE
0x1284c  br       loc_13017
0x12851  ldloc.s  5
0x12853  ldc.i4   0x1FF5
0x12858  bgt.s    loc_12883
0x1285a  ldloc.s  5
0x1285c  ldc.i4   0xBC0
0x12861  beq      loc_12F71
0x12866  ldloc.s  5
0x12868  ldc.i4   0x125F
0x1286d  beq      loc_12B6C
0x12872  ldloc.s  5
0x12874  ldc.i4   0x1FF5
0x12879  beq      loc_12C7E
0x1287e  br       loc_13017
0x12883  ldloc.s  5
0x12885  ldc.i4   0x24B8
0x1288a  bgt.s    loc_128A9
0x1288c  ldloc.s  5
0x1288e  ldc.i4   0x2454
0x12893  beq      loc_12DC8
0x12898  ldloc.s  5
0x1289a  ldc.i4   0x24B8
0x1289f  beq      loc_12E4B
0x128a4  br       loc_13017
0x128a9  ldloc.s  5
0x128ab  ldc.i4   0x2580
0x128b0  beq      loc_12BDE
0x128b5  ldloc.s  5
0x128b7  ldc.i4   0x25E4
0x128bc  beq      loc_12D1B
0x128c1  br       loc_13017
0x128c6  ldarg.0
0x128c7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Dialogs.DeactivateDialogPage::FormTextTitle
0x128cc  ldstr    aWebGridCmdsDlg_40// "Web._grid.cmds.dlg_deactivate.aspx_77_T"...
0x128d1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x128d6  ldarg.0
0x128d7  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Dialogs.DeactivateDialogPage::FormTextOkCancelDiv
0x128dc  ldc.i4.0
0x128dd  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x128e2  ldloc.2
0x128e3  ldloc.0
0x128e4  ldarg.0
0x128e5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x128ea  ldstr    aDialogGridDeac// "Dialog_Grid_Deactivate_Title"
0x128ef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x128f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x128f9  ldc.i4.1
0x128fa  newarr   [mscorlib]System.Object
0x128ff  dup
0x12900  ldc.i4.0
0x12901  ldarg.0
0x12902  ldfld    string Microsoft.Crm.Dialogs.DeactivateDialogPage::ObjName
0x12907  stelem.ref
0x12908  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1290d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x12912  ldloc.2
0x12913  ldloc.0
0x12914  ldarg.0
0x12915  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1291a  ldstr    aDialogDeactiva_2// "Dialog_Deactivate_Description"
0x1291f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x12924  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12929  ldc.i4.2
0x1292a  newarr   [mscorlib]System.Object
0x1292f  dup
0x12930  ldc.i4.0
0x12931  ldarg.0
0x12932  ldflda   int32 Microsoft.Crm.Dialogs.DeactivateDialogPage::iTotal
0x12937  ldloc.0
0x12938  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1293d  stelem.ref
0x1293e  dup
0x1293f  ldc.i4.1
0x12940  ldarg.0
0x12941  ldfld    string Microsoft.Crm.Dialogs.DeactivateDialogPage::ObjNamePlural
0x12946  stelem.ref
0x12947  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1294c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x12951  br       loc_1313B
0x12956  ldarg.0
0x12957  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Dialogs.DeactivateDialogPage::FormTextTitle
0x1295c  ldstr    aWebGridCmdsDlg_41// "Web._grid.cmds.dlg_deactivate.aspx_78_T"...
0x12961  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x12966  ldarg.0
0x12967  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Dialogs.DeactivateDialogPage::FormTextOkCancelDiv
0x1296c  ldc.i4.0
0x1296d  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x12972  ldloc.2
0x12973  ldloc.0
0x12974  ldarg.0
0x12975  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1297a  ldstr    aDialogGridDeac// "Dialog_Grid_Deactivate_Title"
0x1297f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x12984  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12989  ldc.i4.1
0x1298a  newarr   [mscorlib]System.Object
0x1298f  dup
0x12990  ldc.i4.0
0x12991  ldarg.0
0x12992  ldfld    string Microsoft.Crm.Dialogs.DeactivateDialogPage::ObjName
0x12997  stelem.ref
0x12998  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1299d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x129a2  ldloc.2
0x129a3  ldloc.0
0x129a4  ldarg.0
0x129a5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x129aa  ldstr    aDialogDeactiva_2// "Dialog_Deactivate_Description"
0x129af  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x129b4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x129b9  ldc.i4.2
0x129ba  newarr   [mscorlib]System.Object
0x129bf  dup
0x129c0  ldc.i4.0
0x129c1  ldarg.0
0x129c2  ldflda   int32 Microsoft.Crm.Dialogs.DeactivateDialogPage::iTotal
0x129c7  ldloc.0
0x129c8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x129cd  stelem.ref
0x129ce  dup
0x129cf  ldc.i4.1
0x129d0  ldarg.0
0x129d1  ldfld    string Microsoft.Crm.Dialogs.DeactivateDialogPage::ObjNamePlural
0x129d6  stelem.ref
0x129d7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x129dc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x129e1  br       loc_1313B
0x129e6  ldarg.0
0x129e7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Dialogs.DeactivateDialogPage::FormTextTitle
0x129ec  ldstr    aWebGridCmdsDlg_42// "Web._grid.cmds.dlg_deactivate.aspx_102_"...
0x129f1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x129f6  ldarg.0
0x129f7  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Dialogs.DeactivateDialogPage::FormTextOkCancelDiv
0x129fc  ldc.i4.0
0x129fd  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x12a02  ldarg.0
0x12a03  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Dialogs.DeactivateDialogPage::FormTextTitle
0x12a08  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x12a0d  ldarg.0
0x12a0e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Dialogs.DeactivateDialogPage::entityType
0x12a13  ldloc.3
0x12a14  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.EntityNameArgument::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x12a19  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x12a1e  ldarg.0
0x12a1f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Dialogs.DeactivateDialogPage::FormTextOk
0x12a24  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x12a29  ldarg.0
0x12a2a  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Dialogs.DeactivateDialogPage::entityType
0x12a2f  ldloc.3
0x12a30  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.EntityNameArgument::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x12a35  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x12a3a  ldarg.0
0x12a3b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Dialogs.DeactivateDialogPage::FormTextCancel
0x12a40  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x12a45  ldarg.0
0x12a46  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Dialogs.DeactivateDialogPage::entityType
0x12a4b  ldloc.3
0x12a4c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.EntityNameArgument::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x12a51  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x12a56  ldloc.2
0x12a57  ldloc.0
0x12a58  ldarg.0
0x12a59  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12a5e  ldstr    aDialogGridDeac// "Dialog_Grid_Deactivate_Title"
0x12a63  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x12a68  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12a6d  ldc.i4.1
0x12a6e  newarr   [mscorlib]System.Object
0x12a73  dup
0x12a74  ldc.i4.0
0x12a75  ldarg.0
0x12a76  ldfld    string Microsoft.Crm.Dialogs.DeactivateDialogPage::ObjName
0x12a7b  stelem.ref
0x12a7c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12a81  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x12a86  ldloc.2
0x12a87  ldloc.0
0x12a88  ldarg.0
0x12a89  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12a8e  ldstr    aDialogDeactiva_2// "Dialog_Deactivate_Description"
0x12a93  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x12a98  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12a9d  ldc.i4.2
0x12a9e  newarr   [mscorlib]System.Object
0x12aa3  dup
0x12aa4  ldc.i4.0
0x12aa5  ldarg.0
0x12aa6  ldflda   int32 Microsoft.Crm.Dialogs.DeactivateDialogPage::iTotal
0x12aab  ldloc.0
0x12aac  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x12ab1  stelem.ref
0x12ab2  dup
0x12ab3  ldc.i4.1
0x12ab4  ldarg.0
0x12ab5  ldfld    string Microsoft.Crm.Dialogs.DeactivateDialogPage::ObjNamePlural
0x12aba  stelem.ref
0x12abb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12ac0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x12ac5  br       loc_1313B
0x12aca  ldarg.0
0x12acb  ldfld    int32 Microsoft.Crm.Dialogs.DeactivateDialogPage::iTotal
0x12ad0  ldc.i4.1
0x12ad1  ble.s    loc_12AE5
0x12ad3  ldarg.0
0x12ad4  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Dialogs.DeactivateDialogPage::FormTextTitle
0x12ad9  ldstr    aDialogConfirma// "Dialog_Confirmation_Message_Deactivate_"...
0x12ade  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x12ae3  br.s     loc_12AF5
0x12ae5  ldarg.0
0x12ae6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Dialogs.DeactivateDialogPage::FormTextTitle
0x12aeb  ldstr    aDialogConfirma_0// "Dialog_Confirmation_Message_Deactivate_"...
0x12af0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x12af5  ldarg.0
0x12af6  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Dialogs.DeactivateDialogPage::FormTextOkCancelDiv
0x12afb  ldc.i4.0
0x12afc  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x12b01  ldloc.2
0x12b02  ldarg.0
0x12b03  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12b08  ldstr    aDialogTitleDea// "Dialog_Title_Deactivate_User"
0x12b0d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12b12  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x12b17  ldloc.2
0x12b18  ldarg.0
0x12b19  ldfld    int32 Microsoft.Crm.Dialogs.DeactivateDialogPage::iTotal
0x12b1e  ldc.i4.1
0x12b1f  beq.s    loc_12B4D
0x12b21  ldarg.0
0x12b22  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12b27  ldstr    aDialogMessageD// "Dialog_Message_Deactivate_User_Plural"
0x12b2c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x12b31  ldc.i4.1
0x12b32  newarr   [mscorlib]System.Object
0x12b37  dup
0x12b38  ldc.i4.0
0x12b39  ldarg.0
0x12b3a  ldflda   int32 Microsoft.Crm.Dialogs.DeactivateDialogPage::iTotal
0x12b3f  ldloc.0
0x12b40  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x12b45  stelem.ref
0x12b46  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x12b4b  br.s     loc_12B62
0x12b4d  ldarg.0
0x12b4e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12b53  ldstr    aDialogMessageD_0// "Dialog_Message_Deactivate_User_Singular"
0x12b58  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x12b5d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12b62  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x12b67  br       loc_1313B
0x12b6c  ldarg.0
  ... truncated ...
```
