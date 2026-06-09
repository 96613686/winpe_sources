# Microsoft.Crm.Dialogs.SetStateDialogPage::ConfigureForm

- ea: `0x6270`
- end: `0x64d4`
- name: `Microsoft.Crm.Dialogs.SetStateDialogPage::ConfigureForm`
- size: `612`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x6270`

## string_xrefs

- `0x6275`: `Scheduled`
- `0x6406`: `Scheduled`
- `0x6295`: `Completed`
- `0x63bc`: `iScheduledState`

## pseudocode

```c

```

## disassembly

```asm
0x6270  ldstr    aActivitypointe// "activitypointer"
0x6275  ldstr    aScheduled// "Scheduled"
0x627a  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x627f  stloc.0
0x6280  ldstr    aActivitypointe// "activitypointer"
0x6285  ldstr    aOpen// "Open"
0x628a  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x628f  stloc.1
0x6290  ldstr    aActivitypointe// "activitypointer"
0x6295  ldstr    aCompleted// "Completed"
0x629a  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x629f  stloc.2
0x62a0  ldstr    aActivitypointe// "activitypointer"
0x62a5  ldstr    aCanceled// "Canceled"
0x62aa  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x62af  stloc.3
0x62b0  ldarg.0
0x62b1  ldarg.0
0x62b2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x62b7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x62bc  ldstr    aSid// "sId"
0x62c1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62c6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x62cb  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.SetStateDialogPage::Id
0x62d0  ldarg.0
0x62d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62d6  ldstr    aSid// "sId"
0x62db  ldarg.0
0x62dc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.SetStateDialogPage::Id
0x62e1  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x62e6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x62eb  ldarg.0
0x62ec  ldarg.0
0x62ed  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x62f2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x62f7  ldstr    aIobjtype// "iObjType"
0x62fc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6301  ldc.i4.7
0x6302  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6307  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x630c  stfld    int32 Microsoft.Crm.Dialogs.SetStateDialogPage::ObjType
0x6311  ldarg.0
0x6312  ldarg.0
0x6313  ldfld    int32 Microsoft.Crm.Dialogs.SetStateDialogPage::ObjType
0x6318  ldc.i4.1
0x6319  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x631e  stfld    string Microsoft.Crm.Dialogs.SetStateDialogPage::ObjName
0x6323  ldarg.0
0x6324  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6329  ldstr    aIobjtype// "iObjType"
0x632e  ldarg.0
0x632f  ldfld    int32 Microsoft.Crm.Dialogs.SetStateDialogPage::ObjType
0x6334  conv.i8
0x6335  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x633a  ldarg.0
0x633b  ldfld    int32 Microsoft.Crm.Dialogs.SetStateDialogPage::ObjType
0x6340  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6345  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x634a  dup
0x634b  isinst   [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase
0x6350  stloc.s  4
0x6352  ldloc.s  4
0x6354  ldarg.0
0x6355  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.SetStateDialogPage::Id
0x635a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x635f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x6364  ldloc.s  4
0x6366  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve()
0x636b  ldloc.s  4
0x636d  ldstr    aStatecode// "statecode"
0x6372  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6377  isinst   [mscorlib]System.String
0x637c  stloc.s  5
0x637e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x6383  ldloc.s  5
0x6385  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x638a  stloc.s  6
0x638c  ldarg.0
0x638d  ldloc.s  4
0x638f  ldstr    aStatuscode// "statuscode"
0x6394  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6399  unbox.any [mscorlib]System.Int32
0x639e  stfld    int32 Microsoft.Crm.Dialogs.SetStateDialogPage::CurrentStatus
0x63a3  ldarg.0
0x63a4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x63a9  ldstr    aIcurrentstate// "iCurrentState"
0x63ae  ldloc.s  6
0x63b0  conv.i8
0x63b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x63b6  ldarg.0
0x63b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x63bc  ldstr    aIscheduledstat// "iScheduledState"
0x63c1  ldloc.1
0x63c2  conv.i8
0x63c3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x63c8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x63cd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x63d2  ldarg.0
0x63d3  ldfld    int32 Microsoft.Crm.Dialogs.SetStateDialogPage::ObjType
0x63d8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x63dd  stloc.s  7
0x63df  ldarg.0
0x63e0  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Dialogs.SetStateDialogPage::statusCode
0x63e5  ldloc.s  7
0x63e7  ldstr    aStatuscode// "statuscode"
0x63ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x63f1  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x63f6  ldloc.s  5
0x63f8  ldstr    aOpen// "Open"
0x63fd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6402  brtrue.s loc_6422
0x6404  ldloc.s  5
0x6406  ldstr    aScheduled// "Scheduled"
0x640b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6410  brtrue.s loc_6422
0x6412  ldloc.s  5
0x6414  ldstr    aCanceled// "Canceled"
0x6419  call     bool [mscorlib]System.String::op_Equality(string, string)
0x641e  brtrue.s loc_6445
0x6420  br.s     loc_645E
0x6422  ldarg.0
0x6423  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Dialogs.SetStateDialogPage::statusCode
0x6428  ldc.i4.4
0x6429  newarr   [mscorlib]System.Int32
0x642e  dup
0x642f  ldc.i4.0
0x6430  ldloc.0
0x6431  stelem.i4
0x6432  dup
0x6433  ldc.i4.1
0x6434  ldloc.1
0x6435  stelem.i4
0x6436  dup
0x6437  ldc.i4.2
0x6438  ldloc.2
0x6439  stelem.i4
0x643a  dup
0x643b  ldc.i4.3
0x643c  ldloc.3
0x643d  stelem.i4
0x643e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x6443  br.s     loc_645E
0x6445  ldarg.0
0x6446  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Dialogs.SetStateDialogPage::statusCode
0x644b  ldc.i4.2
0x644c  newarr   [mscorlib]System.Int32
0x6451  dup
0x6452  ldc.i4.0
0x6453  ldloc.0
0x6454  stelem.i4
0x6455  dup
0x6456  ldc.i4.1
0x6457  ldloc.3
0x6458  stelem.i4
0x6459  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x645e  ldarg.0
0x645f  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Dialogs.SetStateDialogPage::statusCode
0x6464  ldarg.0
0x6465  ldfld    int32 Microsoft.Crm.Dialogs.SetStateDialogPage::CurrentStatus
0x646a  box      [mscorlib]System.Int32
0x646f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x6474  ldarg.0
0x6475  ldarg.0
0x6476  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x647b  ldstr    aDialogTitleCha// "Dialog_Title_Change_State"
0x6480  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6485  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x648a  ldarg.0
0x648b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x6490  ldarg.0
0x6491  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6496  ldstr    aDialogDescript// "Dialog_Description_Change_Status"
0x649b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x64a0  ldc.i4.1
0x64a1  newarr   [mscorlib]System.Object
0x64a6  dup
0x64a7  ldc.i4.0
0x64a8  ldarg.0
0x64a9  ldfld    string Microsoft.Crm.Dialogs.SetStateDialogPage::ObjName
0x64ae  stelem.ref
0x64af  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x64b4  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x64b9  ldarg.0
0x64ba  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x64bf  ldc.i4.1
0x64c0  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x64c5  pop
0x64c6  ldarg.0
0x64c7  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x64cc  ldc.i4.2
0x64cd  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x64d2  pop
0x64d3  ret
```
