# Microsoft.Crm.Service.Dialogs.RunRoutingWorkflow::ConfigureForm

- ea: `0x20b0`
- end: `0x2343`
- name: `Microsoft.Crm.Service.Dialogs.RunRoutingWorkflow::ConfigureForm`
- size: `659`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x20b0`

## string_xrefs

- `0x216f`: `XML loaded from the stream returned String.Empty.`
- `0x2179`: `XML loaded from the stream returned String.Empty.`

## pseudocode

```c

```

## disassembly

```asm
0x20b0  ldarg.0
0x20b1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x20b6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x20bb  ldstr    aItotal// "iTotal"
0x20c0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x20c5  ldc.i4.7
0x20c6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20cb  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x20d0  stloc.0
0x20d1  ldc.i4.0
0x20d2  stloc.1
0x20d3  ldarg.0
0x20d4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x20d9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x20de  ldstr    aSstatecode// "sStateCode"
0x20e3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x20e8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x20ed  brtrue.s loc_2110
0x20ef  ldarg.0
0x20f0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x20f5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x20fa  ldstr    aSstatecode// "sStateCode"
0x20ff  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2104  ldc.i4.7
0x2105  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x210a  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x210f  stloc.1
0x2110  ldarg.0
0x2111  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x2116  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x211b  stloc.2
0x211c  ldloc.2
0x211d  ldc.i4.0
0x211e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x2123  ldloc.2
0x2124  ldc.i4.1
0x2125  ldstr    aButtonLabelRou// "Button_Label_Route"
0x212a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x212f  ldloc.2
0x2130  ldc.i4.2
0x2131  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x2136  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x213b  ldarg.0
0x213c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2141  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x2146  stloc.3
0x2147  ldloc.3
0x2148  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x214d  ldc.i4.0
0x214e  conv.i8
0x214f  ble      loc_229F
0x2154  ldloc.3
0x2155  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x215a  stloc.s  4
0x215c  ldloc.s  4
0x215e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2163  brtrue.s loc_2189
0x2165  ldloc.s  4
0x2167  callvirt instance int32 [mscorlib]System.String::get_Length()
0x216c  ldc.i4.0
0x216d  cgt.un
0x216f  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x2174  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x2179  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x217e  ldc.i4   0x80049002
0x2183  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2188  throw
0x2189  ldstr    aRoutingrule// "routingrule"
0x218e  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x2193  dup
0x2194  ldc.i4.1
0x2195  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Distinct(bool)
0x219a  dup
0x219b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x21a0  ldstr    aWorkflowid// "workflowid"
0x21a5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x21aa  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x21af  stloc.s  5
0x21b1  ldloc.s  5
0x21b3  ldc.i4.0
0x21b4  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x21b9  ldloc.s  5
0x21bb  ldstr    aStatuscode// "statuscode"
0x21c0  ldc.i4.0
0x21c1  ldc.i4.2
0x21c2  box      RoutingRuleStatus
0x21c7  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x21cc  dup
0x21cd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x21d2  ldloc.s  5
0x21d4  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x21d9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21de  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21e3  stloc.s  6
0x21e5  ldloc.s  6
0x21e7  brfalse.s loc_21F2
0x21e9  ldloc.s  6
0x21eb  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x21f0  brtrue.s loc_220D
0x21f2  ldarg.0
0x21f3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x21f8  ldstr    aDlgRoutecaseVa// "Dlg_RouteCase_Validation_ActiveRouteRul"...
0x21fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2202  ldc.i4   0x8063111A
0x2207  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x220c  throw
0x220d  ldloc.s  6
0x220f  ldc.i4.0
0x2210  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x2215  stloc.s  7
0x2217  ldarg.0
0x2218  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x221d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2222  ldstr    aIid// "iId"
0x2227  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x222c  stloc.s  8
0x222e  ldloc.s  8
0x2230  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2235  brtrue.s loc_228C
0x2237  ldloca.s 9
0x2239  ldloc.s  7
0x223b  ldstr    aWorkflowid// "workflowid"
0x2240  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2245  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x224a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x224f  call     instance void [mscorlib]System.Guid::.ctor(string)
0x2254  ldloca.s 0xA
0x2256  ldloc.s  8
0x2258  call     instance void [mscorlib]System.Guid::.ctor(string)
0x225d  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection::.ctor()
0x2262  stloc.s  0xB
0x2264  ldloc.s  0xB
0x2266  ldstr    aUiscriptInputI// "UIScript_Input_Integer_IsManualRun"
0x226b  ldc.i4.1
0x226c  box      [mscorlib]System.Int32
0x2271  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection::Add(string, object)
0x2276  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x227b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationSdkCommand::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2280  ldloc.s  0xA
0x2282  ldloc.s  9
0x2284  ldloc.s  0xB
0x2286  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationSdkCommandBase::ExecuteWorkflow(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection)
0x228b  pop
0x228c  ldarg.0
0x228d  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x2292  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x2297  leave.s  loc_22AB
0x2299  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x229e  throw
0x229f  leave.s  loc_22AB
0x22a1  ldloc.3
0x22a2  brfalse.s loc_22AA
0x22a4  ldloc.3
0x22a5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22aa  endfinally
0x22ab  ldloc.0
0x22ac  ldc.i4.1
0x22ad  bgt.s    loc_22F7
0x22af  ldloc.1
0x22b0  brtrue.s loc_22CA
0x22b2  ldarg.0
0x22b3  ldarg.0
0x22b4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x22b9  ldstr    aDlgSaveandrout// "Dlg_SaveAndRouteCase_AddRequiredConfirm"...
0x22be  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22c3  stfld    string Microsoft.Crm.Service.Dialogs.RunRoutingWorkflow::dialogBody
0x22c8  br.s     loc_22E0
0x22ca  ldarg.0
0x22cb  ldarg.0
0x22cc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x22d1  ldstr    aDlgRoutecaseAd// "Dlg_RouteCase_AddRequiredConfirmForSing"...
0x22d6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22db  stfld    string Microsoft.Crm.Service.Dialogs.RunRoutingWorkflow::dialogBody
0x22e0  ldloc.2
0x22e1  ldarg.0
0x22e2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x22e7  ldstr    aDlgRoutecaseAd_0// "Dlg_RouteCase_AddRequiredConfirm_Title"
0x22ec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22f1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x22f6  ret
0x22f7  ldloc.2
0x22f8  ldarg.0
0x22f9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x22fe  ldstr    aDlgRoutecaseAd_1// "Dlg_RouteCase_AddRequiredConfirmForMult"...
0x2303  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2308  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x230d  ldarg.0
0x230e  ldarg.0
0x230f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2314  ldstr    aDlgRoutecaseAd_2// "Dlg_RouteCase_AddRequiredConfirmForMult"...
0x2319  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x231e  ldc.i4.1
0x231f  newarr   [mscorlib]System.Object
0x2324  dup
0x2325  ldc.i4.0
0x2326  ldloca.s 0
0x2328  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x232d  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserUICulture()
0x2332  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2337  stelem.ref
0x2338  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x233d  stfld    string Microsoft.Crm.Service.Dialogs.RunRoutingWorkflow::dialogBody
0x2342  ret
```
