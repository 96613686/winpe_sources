# Microsoft.Crm.Dialogs.AssignQueuePage::ConfigureForm

- ea: `0x25b0`
- end: `0x2865`
- name: `Microsoft.Crm.Dialogs.AssignQueuePage::ConfigureForm`
- size: `693`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x25b0`

## pseudocode

```c

```

## disassembly

```asm
0x25b0  ldarg.0
0x25b1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x25b6  ldarg.0
0x25b7  ldarg.0
0x25b8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x25bd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x25c2  ldstr    aItotal// "iTotal"
0x25c7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x25cc  ldc.i4.7
0x25cd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25d2  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x25d7  stfld    int32 Microsoft.Crm.Dialogs.AssignQueuePage::iTotal
0x25dc  ldarg.0
0x25dd  ldarg.0
0x25de  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x25e3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x25e8  ldstr    aIobjtype// "iObjType"
0x25ed  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x25f2  ldc.i4.7
0x25f3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25f8  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x25fd  stfld    int32 Microsoft.Crm.Dialogs.AssignQueuePage::ObjType
0x2602  ldarg.0
0x2603  ldarg.0
0x2604  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2609  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x260e  ldstr    aSsrcid// "sSrcId"
0x2613  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2618  stfld    string Microsoft.Crm.Dialogs.AssignQueuePage::CustParams
0x261d  ldarg.0
0x261e  ldarg.0
0x261f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2624  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2629  ldstr    aSrcqueueid// "srcQueueId"
0x262e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2633  stfld    string Microsoft.Crm.Dialogs.AssignQueuePage::sourceQueueId
0x2638  ldarg.0
0x2639  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x263e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2643  ldstr    aSqtype// "sQType"
0x2648  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x264d  ldnull
0x264e  cgt.un
0x2650  ldstr    aYouMustSpecify// "You must specify a queue type to route "...
0x2655  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x265a  ldarg.0
0x265b  ldtoken  QTypes
0x2660  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2665  ldarg.0
0x2666  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x266b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2670  ldstr    aSqtype// "sQType"
0x2675  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x267a  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x267f  unbox.any QTypes
0x2684  stfld    valuetype QTypes Microsoft.Crm.Dialogs.AssignQueuePage::qtype
0x2689  ldarg.0
0x268a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x268f  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x2694  stloc.0
0x2695  ldloc.0
0x2696  ldc.i4   0x1C2
0x269b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_Width(int32)
0x26a0  ldloc.0
0x26a1  ldc.i4   0x136
0x26a6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_Height(int32)
0x26ab  ldloc.0
0x26ac  ldc.i4.s 0x20
0x26ae  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x26b3  ldloc.0
0x26b4  ldc.i4.1
0x26b5  ldstr    aButtonLabelAss// "Button_Label_Assign"
0x26ba  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x26bf  ldloc.0
0x26c0  ldc.i4.2
0x26c1  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x26c6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x26cb  ldarg.0
0x26cc  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.AssignQueuePage::crmOwnerLookup
0x26d1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x26d6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x26db  ldarg.0
0x26dc  ldfld    int32 Microsoft.Crm.Dialogs.AssignQueuePage::ObjType
0x26e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x26e6  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x26eb  call     instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x26f0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x26f5  ldstr    aOwnerid// "ownerid"
0x26fa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x26ff  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x2704  ldarg.0
0x2705  ldfld    valuetype QTypes Microsoft.Crm.Dialogs.AssignQueuePage::qtype
0x270a  ldc.i4.1
0x270b  ceq
0x270d  ldstr    aYouMustSpecify_0// "You must specify a public queue type on"...
0x2712  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x2717  ldloc.0
0x2718  ldarg.0
0x2719  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x271e  ldstr    aDialogAssignqu// "Dialog_AssignQueue_Title"
0x2723  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2728  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x272d  ldarg.0
0x272e  ldfld    int32 Microsoft.Crm.Dialogs.AssignQueuePage::iTotal
0x2733  ldc.i4.1
0x2734  bne.un.s loc_2766
0x2736  ldloc.0
0x2737  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x273c  ldarg.0
0x273d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2742  ldstr    aDialogAssignqu_0// "Dialog_AssignQueue_Description_Single"
0x2747  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x274c  ldc.i4.1
0x274d  newarr   [mscorlib]System.Object
0x2752  dup
0x2753  ldc.i4.0
0x2754  ldstr    a1// "1"
0x2759  stelem.ref
0x275a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x275f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x2764  br.s     loc_27A4
0x2766  ldloc.0
0x2767  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x276c  ldarg.0
0x276d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2772  ldstr    aDialogAssignqu_1// "Dialog_AssignQueue_Description_Plural"
0x2777  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x277c  ldc.i4.1
0x277d  newarr   [mscorlib]System.Object
0x2782  dup
0x2783  ldc.i4.0
0x2784  ldarg.0
0x2785  ldflda   int32 Microsoft.Crm.Dialogs.AssignQueuePage::iTotal
0x278a  ldstr    aD// "D"
0x278f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x2794  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x2799  stelem.ref
0x279a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x279f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x27a4  ldstr    a112112// "(^(112\\,)*112$)"
0x27a9  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string)
0x27ae  stloc.1
0x27af  ldc.i4.s 0x70
0x27b1  ldarg.0
0x27b2  ldfld    int32 Microsoft.Crm.Dialogs.AssignQueuePage::ObjType
0x27b7  beq.s    loc_27E3
0x27b9  ldc.i4   0x7ED
0x27be  ldarg.0
0x27bf  ldfld    int32 Microsoft.Crm.Dialogs.AssignQueuePage::ObjType
0x27c4  bne.un.s loc_2831
0x27c6  ldloc.1
0x27c7  ldarg.0
0x27c8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x27cd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x27d2  ldstr    aSsubtypes// "sSubTypes"
0x27d7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x27dc  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x27e1  brfalse.s loc_2831
0x27e3  ldarg.0
0x27e4  ldarg.0
0x27e5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x27ea  ldstr    aWebGridCmdsDlg_7// "Web._grid.cmds.dlg_assign.aspx_104"
0x27ef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27f4  stfld    string Microsoft.Crm.Dialogs.AssignQueuePage::_headerText0
0x27f9  ldarg.0
0x27fa  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x27ff  ldarg.0
0x2800  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2805  ldstr    aWebGridCmdsDlg_8// "Web._grid.cmds.dlg_assign.aspx_106"
0x280a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x280f  ldc.i4.1
0x2810  newarr   [mscorlib]System.Object
0x2815  dup
0x2816  ldc.i4.0
0x2817  ldc.i4.s 0x70
0x2819  ldc.i4.1
0x281a  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x281f  stelem.ref
0x2820  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2825  stfld    string Microsoft.Crm.Dialogs.AssignQueuePage::_descriptionText0
0x282a  ldarg.0
0x282b  ldc.i4.1
0x282c  stfld    bool Microsoft.Crm.Dialogs.AssignQueuePage::bUseAssignToMeRadioButtons
0x2831  ldarg.0
0x2832  ldarg.0
0x2833  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2838  ldstr    aDialogAssignqu_2// "Dialog_AssignQueue_Assign_Label"
0x283d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2842  stfld    string Microsoft.Crm.Dialogs.AssignQueuePage::_headerText1
0x2847  ldarg.0
0x2848  ldarg.0
0x2849  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x284e  ldstr    aDialogAssignqu_3// "Dialog_AssignQueue_Assign_LabelDetails"
0x2853  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2858  stfld    string Microsoft.Crm.Dialogs.AssignQueuePage::_descriptionText1
0x285d  ldarg.0
0x285e  ldc.i4.1
0x285f  stfld    bool Microsoft.Crm.Dialogs.AssignQueuePage::bLookup
0x2864  ret
```
