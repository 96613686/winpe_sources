# Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::ConfigureHeader

- ea: `0xfbb0`
- end: `0x1020b`
- name: `Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::ConfigureHeader`
- size: `1627`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xfbb0`

## string_xrefs

- `0xff2e`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xff3e`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0xfbbc`: `InteractiveWorkflowWebService`
- `0xff14`: `/_controls/CompositeControl/CompositeControl.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0xfbb0  ldarg.0
0xfbb1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0xfbb6  ldarg.0
0xfbb7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfbbc  ldstr    aInteractivewor// "InteractiveWorkflowWebService"
0xfbc1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfbc6  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor()
0xfbcb  stloc.0
0xfbcc  ldloc.0
0xfbcd  ldstr    aName// "name"
0xfbd2  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xfbd7  ldloc.0
0xfbd8  ldstr    aStatecode// "statecode"
0xfbdd  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xfbe2  ldloc.0
0xfbe3  ldstr    aOwnerid// "ownerid"
0xfbe8  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xfbed  ldloc.0
0xfbee  ldstr    aActiveworkflow// "activeworkflowid"
0xfbf3  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xfbf8  ldloc.0
0xfbf9  ldstr    aSubprocess// "subprocess"
0xfbfe  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xfc03  ldloc.0
0xfc04  ldstr    aInputparameter// "inputparameters"
0xfc09  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xfc0e  ldloc.0
0xfc0f  ldstr    aType// "type"
0xfc14  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xfc19  ldloc.0
0xfc1a  ldstr    aCategory// "category"
0xfc1f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xfc24  ldnull
0xfc25  stloc.1
0xfc26  ldstr    aWorkflow_0// "workflow"
0xfc2b  ldarg.0
0xfc2c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::interactiveWorkflowId
0xfc31  ldloc.0
0xfc32  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfc37  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfc3c  stloc.1
0xfc3d  leave.s  loc_FC97
0xfc3f  stloc.s  9
0xfc41  ldarg.0
0xfc42  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xfc47  callvirt instance void [System.Web]System.Web.HttpResponse::ClearContent()
0xfc4c  ldstr    aCsDialogsUiscr// "/cs/dialogs/uiscripterror.aspx"
0xfc51  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfc56  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfc5b  stloc.s  0xA
0xfc5d  ldloc.s  0xA
0xfc5f  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xfc64  ldstr    aHresult// "hresult"
0xfc69  ldloc.s  9
0xfc6b  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0xfc70  stloc.s  0xB
0xfc72  ldloca.s 0xB
0xfc74  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfc79  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xfc7e  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xfc83  ldarg.0
0xfc84  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xfc89  ldloc.s  0xA
0xfc8b  callvirt instance string [mscorlib]System.Object::ToString()
0xfc90  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0xfc95  leave.s  loc_FC97
0xfc97  ldloc.1
0xfc98  ldstr    aName// "name"
0xfc9d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xfca2  castclass [mscorlib]System.String
0xfca7  stloc.2
0xfca8  ldloc.1
0xfca9  ldstr    aStatecode// "statecode"
0xfcae  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xfcb3  castclass [mscorlib]System.String
0xfcb8  stloc.3
0xfcb9  ldloc.1
0xfcba  ldstr    aOwnerid// "ownerid"
0xfcbf  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xfcc4  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xfcc9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Name()
0xfcce  stloc.s  4
0xfcd0  ldloc.1
0xfcd1  ldstr    aInputparameter// "inputparameters"
0xfcd6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xfcdb  castclass [mscorlib]System.String
0xfce0  stloc.s  5
0xfce2  ldc.i4.0
0xfce3  stloc.s  6
0xfce5  ldloc.s  5
0xfce7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfcec  brtrue.s loc_FD04
0xfcee  ldloc.s  5
0xfcf0  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xfcf5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xfcfa  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0xfcff  brfalse.s loc_FD04
0xfd01  ldc.i4.1
0xfd02  stloc.s  6
0xfd04  ldloc.1
0xfd05  ldstr    aType// "type"
0xfd0a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xfd0f  unbox.any [mscorlib]System.Int32
0xfd14  stloc.s  7
0xfd16  ldloc.1
0xfd17  ldstr    aCategory// "category"
0xfd1c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xfd21  unbox.any [mscorlib]System.Int32
0xfd26  stloc.s  8
0xfd28  ldc.i4.1
0xfd29  ldloc.s  8
0xfd2b  beq.s    loc_FD7D
0xfd2d  ldarg.0
0xfd2e  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xfd33  callvirt instance void [System.Web]System.Web.HttpResponse::ClearContent()
0xfd38  ldstr    aCsDialogsUiscr// "/cs/dialogs/uiscripterror.aspx"
0xfd3d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfd42  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfd47  stloc.s  0xC
0xfd49  ldloc.s  0xC
0xfd4b  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xfd50  ldstr    aCustomerror// "customError"
0xfd55  ldc.i4.6
0xfd56  stloc.s  0xD
0xfd58  ldloca.s 0xD
0xfd5a  constrained. Microsoft.Crm.Service.Web.CS.CustomUIScriptErrors
0xfd60  callvirt instance string [mscorlib]System.Object::ToString()
0xfd65  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xfd6a  ldarg.0
0xfd6b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xfd70  ldloc.s  0xC
0xfd72  callvirt instance string [mscorlib]System.Object::ToString()
0xfd77  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0xfd7c  ret
0xfd7d  ldloc.s  7
0xfd7f  ldc.i4.3
0xfd80  bne.un.s loc_FDD2
0xfd82  ldarg.0
0xfd83  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xfd88  callvirt instance void [System.Web]System.Web.HttpResponse::ClearContent()
0xfd8d  ldstr    aCsDialogsUiscr// "/cs/dialogs/uiscripterror.aspx"
0xfd92  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfd97  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfd9c  stloc.s  0xE
0xfd9e  ldloc.s  0xE
0xfda0  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xfda5  ldstr    aCustomerror// "customError"
0xfdaa  ldc.i4.4
0xfdab  stloc.s  0xD
0xfdad  ldloca.s 0xD
0xfdaf  constrained. Microsoft.Crm.Service.Web.CS.CustomUIScriptErrors
0xfdb5  callvirt instance string [mscorlib]System.Object::ToString()
0xfdba  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xfdbf  ldarg.0
0xfdc0  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xfdc5  ldloc.s  0xE
0xfdc7  callvirt instance string [mscorlib]System.Object::ToString()
0xfdcc  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0xfdd1  ret
0xfdd2  ldloc.s  6
0xfdd4  brfalse.s loc_FE26
0xfdd6  ldarg.0
0xfdd7  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xfddc  callvirt instance void [System.Web]System.Web.HttpResponse::ClearContent()
0xfde1  ldstr    aCsDialogsUiscr// "/cs/dialogs/uiscripterror.aspx"
0xfde6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfdeb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfdf0  stloc.s  0xF
0xfdf2  ldloc.s  0xF
0xfdf4  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xfdf9  ldstr    aCustomerror// "customError"
0xfdfe  ldc.i4.7
0xfdff  stloc.s  0xD
0xfe01  ldloca.s 0xD
0xfe03  constrained. Microsoft.Crm.Service.Web.CS.CustomUIScriptErrors
0xfe09  callvirt instance string [mscorlib]System.Object::ToString()
0xfe0e  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xfe13  ldarg.0
0xfe14  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xfe19  ldloc.s  0xF
0xfe1b  callvirt instance string [mscorlib]System.Object::ToString()
0xfe20  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0xfe25  ret
0xfe26  ldloc.3
0xfe27  ldc.i4.1
0xfe28  stloc.s  0x10
0xfe2a  ldloca.s 0x10
0xfe2c  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.WorkflowState
0xfe32  callvirt instance string [mscorlib]System.Object::ToString()
0xfe37  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xfe3c  brfalse.s loc_FE8E
0xfe3e  ldarg.0
0xfe3f  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xfe44  callvirt instance void [System.Web]System.Web.HttpResponse::ClearContent()
0xfe49  ldstr    aCsDialogsUiscr// "/cs/dialogs/uiscripterror.aspx"
0xfe4e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfe53  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfe58  stloc.s  0x11
0xfe5a  ldloc.s  0x11
0xfe5c  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xfe61  ldstr    aCustomerror// "customError"
0xfe66  ldc.i4.1
0xfe67  stloc.s  0xD
0xfe69  ldloca.s 0xD
0xfe6b  constrained. Microsoft.Crm.Service.Web.CS.CustomUIScriptErrors
0xfe71  callvirt instance string [mscorlib]System.Object::ToString()
0xfe76  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xfe7b  ldarg.0
0xfe7c  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xfe81  ldloc.s  0x11
0xfe83  callvirt instance string [mscorlib]System.Object::ToString()
0xfe88  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0xfe8d  ret
0xfe8e  ldarg.0
0xfe8f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfe94  ldloc.2
0xfe95  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xfe9a  ldloc.1
0xfe9b  ldstr    aActiveworkflow// "activeworkflowid"
0xfea0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xfea5  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xfeaa  stloc.s  0x12
0xfeac  ldarg.0
0xfead  ldloc.s  0x12
0xfeaf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xfeb4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xfeb9  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::interactiveWorkflowId
0xfebe  ldarg.0
0xfebf  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0xfec4  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm
0xfec9  dup
0xfeca  ldloc.2
0xfecb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::set_PageTitle(string)
0xfed0  ldsfld   string [mscorlib]System.String::Empty
0xfed5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::set_PageDescription(string)
0xfeda  ldarg.0
0xfedb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfee0  ldstr    aCsDialogDialog// "/cs/dialog/dialogstyles.css.aspx"
0xfee5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfeea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfeef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xfef4  ldarg.0
0xfef5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfefa  ldstr    aControlsNotifi// "/_controls/notifications/notifications."...
0xfeff  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xff04  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xff09  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xff0e  ldarg.0
0xff0f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff14  ldstr    aControlsCompos// "/_controls/CompositeControl/CompositeCo"...
0xff19  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xff1e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xff23  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xff28  ldarg.0
0xff29  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff2e  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/CrmInternalUti"...
0xff33  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff38  ldarg.0
0xff39  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff3e  ldstr    aStaticCommonSc_9// "/_static/_common/scripts/Mscrm.Caching."...
0xff43  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff48  ldarg.0
0xff49  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff4e  ldstr    aStaticControls_8// "/_static/_controls/UIScripts/UIScriptUt"...
0xff53  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xff58  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xff5d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xff62  ldarg.0
0xff63  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff68  ldstr    aStaticFormsNum// "/_static/_forms/NumberInputBehavior.js"
0xff6d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff72  ldarg.0
0xff73  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff78  ldstr    aStaticFormsTex// "/_static/_forms/TextInputBehavior.js"
0xff7d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff82  ldarg.0
0xff83  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff88  ldstr    aStaticFormsLoo_0// "/_static/_forms/LookupBehavior.js"
0xff8d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff92  ldarg.0
0xff93  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::hiddenDateTime
0xff98  ldstr    aDatetime// "datetime"
0xff9d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0xffa2  ldarg.0
0xffa3  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::hiddenDateTime
0xffa8  ldc.i4.1
0xffa9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_ShowTime(bool)
0xffae  ldarg.0
0xffaf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xffb4  ldstr    aWebwizardWizar// "/WebWizard/WizardForm.css.aspx"
0xffb9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xffbe  ldarg.0
0xffbf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xffc4  ldstr    aInitialScriptI// "INITIAL_SCRIPT_ID"
0xffc9  ldarg.0
0xffca  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::interactiveWorkflowId
0xffcf  constrained. [mscorlib]System.Guid
0xffd5  callvirt instance string [mscorlib]System.Object::ToString()
0xffda  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xffdf  ldarg.0
  ... truncated ...
```
