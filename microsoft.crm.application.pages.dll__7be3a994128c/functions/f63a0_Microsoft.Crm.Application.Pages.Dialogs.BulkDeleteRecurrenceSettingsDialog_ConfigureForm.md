# Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::ConfigureForm

- ea: `0xf63a0`
- end: `0xf69d6`
- name: `Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::ConfigureForm`
- size: `1590`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0xf6260`
- `0xf63a0`
- `0xf69e0`
- `0xf6be0`
- `0xf6c30`

## string_xrefs

- `0xf6492`: `text/xml`
- `0xf64d1`: `XML loaded from the stream returned String.Empty.`
- `0xf64db`: `XML loaded from the stream returned String.Empty.`
- `0xf65d0`: `BulkDeleteSettings_DialogTitle`
- `0xf66bf`: `BulkDeleteSettings_DialogDescription`
- `0xf66d5`: `BulkDeleteSettings.aspx_HeaderLabel`

## pseudocode

```c

```

## disassembly

```asm
0xf63a0  ldarg.0
0xf63a1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xf63a6  ldarg.0
0xf63a7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf63ac  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0xf63b1  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0xf63b6  ldc.i4.0
0xf63b7  conv.i8
0xf63b8  ble      loc_F65B3
0xf63bd  ldarg.0
0xf63be  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf63c3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf63c8  ldstr    aRecpattern// "recPattern"
0xf63cd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf63d2  stloc.0
0xf63d3  ldarg.0
0xf63d4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf63d9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf63de  ldstr    aRecstarttime// "recStartTime"
0xf63e3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf63e8  stloc.1
0xf63e9  ldloca.s 2
0xf63eb  ldarg.0
0xf63ec  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf63f1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf63f6  ldstr    aIid// "iId"
0xf63fb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf6400  call     instance void [mscorlib]System.Guid::.ctor(string)
0xf6405  ldloc.2
0xf6406  stloc.3
0xf6407  ldarg.0
0xf6408  ldfld    int32 Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::objType
0xf640d  ldc.i4   0x1148
0xf6412  bne.un.s loc_F641C
0xf6414  ldarg.0
0xf6415  ldloc.2
0xf6416  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::GetAsyncId(valuetype [mscorlib]System.Guid bulkDeleteId)
0xf641b  stloc.2
0xf641c  ldloc.1
0xf641d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf6422  brfalse  loc_F64EB
0xf6427  ldarg.0
0xf6428  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf642d  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0xf6432  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0xf6437  stloc.s  4
0xf6439  ldloc.s  4
0xf643b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf6440  brtrue   loc_F64C7
0xf6445  ldc.i4   0x125C
0xf644a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf644f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf6454  dup
0xf6455  ldloca.s 2
0xf6457  constrained. [mscorlib]System.Guid
0xf645d  callvirt instance string [mscorlib]System.Object::ToString()
0xf6462  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0xf6467  dup
0xf6468  ldstr    aStatecode// "statecode"
0xf646d  ldc.i4.3
0xf646e  stloc.s  5
0xf6470  ldloca.s 5
0xf6472  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.AsyncOperationState
0xf6478  callvirt instance string [mscorlib]System.Object::ToString()
0xf647d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xf6482  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf6487  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf648c  ldarg.0
0xf648d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xf6492  ldstr    aTextXml// "text/xml"
0xf6497  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0xf649c  ldarg.0
0xf649d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xf64a2  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0xf64a7  ldarg.0
0xf64a8  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xf64ad  ldstr    aOk// "<ok/>"
0xf64b2  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0xf64b7  ldarg.0
0xf64b8  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xf64bd  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0xf64c2  br       loc_F65A8
0xf64c7  ldloc.s  4
0xf64c9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf64ce  ldc.i4.0
0xf64cf  ceq
0xf64d1  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0xf64d6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xf64db  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0xf64e0  ldc.i4   0x80049002
0xf64e5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xf64ea  throw
0xf64eb  ldloc.0
0xf64ec  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf64f1  brfalse.s loc_F6534
0xf64f3  ldsfld   string [mscorlib]System.String::Empty
0xf64f8  stloc.0
0xf64f9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0xf64fe  brfalse.s loc_F6534
0xf6500  ldarg.0
0xf6501  ldfld    int32 Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::objType
0xf6506  ldc.i4   0x1148
0xf650b  bne.un.s loc_F6534
0xf650d  ldc.i4   0x1148
0xf6512  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf6517  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf651c  dup
0xf651d  ldloca.s 3
0xf651f  constrained. [mscorlib]System.Guid
0xf6525  callvirt instance string [mscorlib]System.Object::ToString()
0xf652a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0xf652f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Delete()
0xf6534  ldloc.1
0xf6535  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf653a  ldc.i4.s 0x10
0xf653c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider, valuetype [mscorlib]System.Globalization.DateTimeStyles)
0xf6541  stloc.s  6
0xf6543  ldloca.s 7
0xf6545  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Today()
0xf654a  stloc.s  8
0xf654c  ldloca.s 8
0xf654e  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xf6553  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Today()
0xf6558  stloc.s  8
0xf655a  ldloca.s 8
0xf655c  call     instance int32 [mscorlib]System.DateTime::get_Month()
0xf6561  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Today()
0xf6566  stloc.s  8
0xf6568  ldloca.s 8
0xf656a  call     instance int32 [mscorlib]System.DateTime::get_Day()
0xf656f  ldloca.s 6
0xf6571  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0xf6576  ldloca.s 6
0xf6578  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0xf657d  ldloca.s 6
0xf657f  call     instance int32 [mscorlib]System.DateTime::get_Second()
0xf6584  ldc.i4.2
0xf6585  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32, valuetype [mscorlib]System.DateTimeKind)
0xf658a  ldloc.2
0xf658b  ldloc.0
0xf658c  ldloc.s  7
0xf658e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf6593  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.UpdateRecurrencePatternCommand::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.DateTime, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf6598  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.UpdateRecurrencePatternCommand::Execute()
0xf659d  ldarg.0
0xf659e  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xf65a3  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0xf65a8  leave    loc_F69D5
0xf65ad  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0xf65b2  throw
0xf65b3  ldarg.0
0xf65b4  ldarg.0
0xf65b5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xf65ba  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xf65bf  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::_Form
0xf65c4  ldarg.0
0xf65c5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::_Form
0xf65ca  ldarg.0
0xf65cb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf65d0  ldstr    aBulkdeletesett// "BulkDeleteSettings_DialogTitle"
0xf65d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf65da  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xf65df  ldnull
0xf65e0  stloc.s  9
0xf65e2  ldarg.0
0xf65e3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf65e8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf65ed  ldstr    aSids// "sIds"
0xf65f2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf65f7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf65fc  brtrue   loc_F66A6
0xf6601  ldloca.s 0xE
0xf6603  ldarg.0
0xf6604  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf6609  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf660e  ldstr    aSids// "sIds"
0xf6613  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf6618  call     instance void [mscorlib]System.Guid::.ctor(string)
0xf661d  ldarg.0
0xf661e  ldfld    int32 Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::objType
0xf6623  ldc.i4   0x1148
0xf6628  bne.un.s loc_F6634
0xf662a  ldarg.0
0xf662b  ldloc.s  0xE
0xf662d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::GetAsyncId(valuetype [mscorlib]System.Guid bulkDeleteId)
0xf6632  stloc.s  0xE
0xf6634  ldc.i4.3
0xf6635  newarr   [mscorlib]System.String
0xf663a  dup
0xf663b  ldc.i4.0
0xf663c  ldstr    aRecurrencepatt// "recurrencepattern"
0xf6641  stelem.ref
0xf6642  dup
0xf6643  ldc.i4.1
0xf6644  ldstr    aRecurrencestar// "recurrencestarttime"
0xf6649  stelem.ref
0xf664a  dup
0xf664b  ldc.i4.2
0xf664c  ldstr    aOperationtype// "operationtype"
0xf6651  stelem.ref
0xf6652  stloc.s  0xF
0xf6654  ldstr    aAsyncoperation_0// "asyncoperation"
0xf6659  ldloc.s  0xE
0xf665b  ldloc.s  0xF
0xf665d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf6662  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf6667  stloc.s  9
0xf6669  ldarg.0
0xf666a  ldloc.s  9
0xf666c  ldstr    aOperationtype// "operationtype"
0xf6671  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xf6676  unbox.any [mscorlib]System.Int32
0xf667b  stfld    int32 Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::asyncType
0xf6680  ldarg.0
0xf6681  ldloc.s  9
0xf6683  call     instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.IRecurrencePattern Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::GetRecurrencePattern(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity asyncOp)
0xf6688  stloc.s  0x10
0xf668a  ldarg.0
0xf668b  ldloc.s  0x10
0xf668d  callvirt instance valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.RecurrenceFrequency [Microsoft.Crm.Core.Extensions]Microsoft.Crm.IRecurrencePattern::get_Frequency()
0xf6692  stloc.s  0x11
0xf6694  ldloca.s 0x11
0xf6696  constrained. [Microsoft.Crm.Core.Extensions]Microsoft.Crm.RecurrenceFrequency
0xf669c  callvirt instance string [mscorlib]System.Object::ToString()
0xf66a1  stfld    string Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::recurrenceSelected
0xf66a6  ldarg.0
0xf66a7  ldfld    int32 Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::objType
0xf66ac  ldc.i4   0x1148
0xf66b1  bne.un.s loc_F66E6
0xf66b3  ldarg.0
0xf66b4  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::_Form
0xf66b9  ldarg.0
0xf66ba  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf66bf  ldstr    aBulkdeletesett_0// "BulkDeleteSettings_DialogDescription"
0xf66c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf66c9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xf66ce  ldarg.0
0xf66cf  ldarg.0
0xf66d0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf66d5  ldstr    aBulkdeletesett_1// "BulkDeleteSettings.aspx_HeaderLabel"
0xf66da  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf66df  stfld    string Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::runJobLabel
0xf66e4  br.s     loc_F6752
0xf66e6  ldarg.0
0xf66e7  call     instance bool Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::get_IsRollupJob()
0xf66ec  brfalse.s loc_F6721
0xf66ee  ldarg.0
0xf66ef  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::_Form
0xf66f4  ldarg.0
0xf66f5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf66fa  ldstr    aModifyrecurren_2// "ModifyRecurrence_RollupCalculation_Dial"...
0xf66ff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf6704  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xf6709  ldarg.0
0xf670a  ldarg.0
0xf670b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf6710  ldstr    aModifyrecurren_3// "ModifyRecurrence_RollupCalculation_Run"
0xf6715  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf671a  stfld    string Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::runJobLabel
0xf671f  br.s     loc_F6752
0xf6721  ldarg.0
0xf6722  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::_Form
0xf6727  ldarg.0
0xf6728  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf672d  ldstr    aModifyrecurren_4// "ModifyRecurrence_DD_DialogDescription"
0xf6732  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf6737  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xf673c  ldarg.0
0xf673d  ldarg.0
0xf673e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf6743  ldstr    aModifyrecurren_5// "ModifyRecurrence_DD_Run"
0xf6748  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf674d  stfld    string Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::runJobLabel
0xf6752  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.NameValuePair>::.ctor()
0xf6757  stloc.s  0xA
0xf6759  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.NameValuePair>::.ctor()
0xf675e  stloc.s  0xB
0xf6760  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.NameValuePair>::.ctor()
0xf6765  stloc.s  0xC
0xf6767  ldarg.0
0xf6768  call     instance bool Microsoft.Crm.Application.Pages.Dialogs.BulkDeleteRecurrenceSettingsDialog::get_IsRollupJob()
0xf676d  brfalse  loc_F6851
0xf6772  ldc.i4.1
0xf6773  stloc.s  0x12
0xf6775  br.s     loc_F67A1
0xf6777  ldloc.s  0xB
0xf6779  ldloca.s 0x12
0xf677b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf6780  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf6785  ldloca.s 0x12
0xf6787  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xf678c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf6791  newobj   instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.NameValuePair::.ctor(string, string)
0xf6796  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.NameValuePair>::Add(var<u1>)
0xf679b  ldloc.s  0x12
0xf679d  ldc.i4.1
0xf679e  add
0xf679f  stloc.s  0x12
0xf67a1  ldloc.s  0x12
0xf67a3  ldc.i4.s 0x18
  ... truncated ...
```
