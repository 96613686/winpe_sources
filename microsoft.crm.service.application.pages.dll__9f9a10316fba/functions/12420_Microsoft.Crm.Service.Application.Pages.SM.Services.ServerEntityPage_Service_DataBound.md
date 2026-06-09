# Microsoft.Crm.Service.Application.Pages.SM.Services.ServerEntityPage::Service_DataBound

- ea: `0x12420`
- end: `0x12636`
- name: `Microsoft.Crm.Service.Application.Pages.SM.Services.ServerEntityPage::Service_DataBound`
- size: `534`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x12420`
- `0x12640`

## string_xrefs

- `0x12500`: `readonly`

## pseudocode

```c

```

## disassembly

```asm
0x12420  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x12425  brtrue.s loc_12442
0x12427  ldarg.2
0x12428  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x1242d  ldstr    aA88fa9436ffb46// "{a88fa943-6ffb-4638-9790-b8ae60dc53bd}"
0x12432  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x12437  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormTab
0x1243c  ldc.i4.0
0x1243d  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x12442  ldarg.2
0x12443  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x12448  ldstr    aIframeRuletree// "IFRAME_RuleTree"
0x1244d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x12452  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl
0x12457  stloc.0
0x12458  ldarg.2
0x12459  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x1245e  ldstr    aResourcespecid// "resourcespecid"
0x12463  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x12468  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl
0x1246d  stloc.1
0x1246e  ldloc.0
0x1246f  brfalse  loc_1252C
0x12474  ldloc.1
0x12475  brfalse  loc_1252C
0x1247a  ldloc.1
0x1247b  callvirt instance object [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0x12480  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x12485  stloc.s  6
0x12487  ldstr    aSmResourcespec_0// "/SM/ResourceSpecs/edit.aspx"
0x1248c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x12491  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12496  stloc.s  7
0x12498  ldloc.s  6
0x1249a  brfalse.s loc_124B6
0x1249c  ldloc.s  7
0x1249e  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x124a3  ldstr    aResourcespecid_0// "resourceSpecId"
0x124a8  ldloc.s  6
0x124aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x124af  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x124b4  br.s     loc_124CC
0x124b6  ldarg.0
0x124b7  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_Notifications()
0x124bc  ldstr    aResourceSelect_5// "Resource_Selection_Notification"
0x124c1  ldc.i4.2
0x124c2  ldstr    aResources_0// "Resources"
0x124c7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::AddNotification(string, int32, string)
0x124cc  ldarg.0
0x124cd  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x124d2  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_ReadOnly()
0x124d7  brtrue.s loc_124F9
0x124d9  ldarg.0
0x124da  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x124df  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x124e4  brtrue.s loc_124F9
0x124e6  ldc.i4   0xFA6
0x124eb  ldc.i4.s 0x10
0x124ed  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x124f2  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x124f7  brtrue.s loc_1250F
0x124f9  ldloc.s  7
0x124fb  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x12500  ldstr    aReadonly// "readonly"
0x12505  ldstr    a1// "1"
0x1250a  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1250f  ldloc.0
0x12510  ldloc.s  7
0x12512  callvirt instance string [mscorlib]System.Object::ToString()
0x12517  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Url(string)
0x1251c  ldloc.0
0x1251d  ldstr    aStyle_0// "style"
0x12522  ldstr    aScrollingNo// "scrolling:no"
0x12527  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0x1252c  ldarg.2
0x1252d  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x12532  ldstr    aGranularity// "granularity"
0x12537  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1253c  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl
0x12541  stloc.2
0x12542  ldarg.2
0x12543  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x12548  ldstr    aDisplaygranula// "displaygranularity"
0x1254d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x12552  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DurationControl
0x12557  stloc.3
0x12558  ldloc.2
0x12559  brfalse.s loc_125AE
0x1255b  ldloc.3
0x1255c  brfalse.s loc_125AE
0x1255e  ldloc.2
0x1255f  callvirt instance object [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0x12564  brfalse.s loc_12578
0x12566  ldloc.2
0x12567  callvirt instance object [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0x1256c  isinst   [mscorlib]System.String
0x12571  callvirt instance int32 [mscorlib]System.String::get_Length()
0x12576  brtrue.s loc_12592
0x12578  ldloc.2
0x12579  ldstr    aFreqMinutelyIn// "FREQ=MINUTELY;INTERVAL=15;"
0x1257e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x12583  ldloc.3
0x12584  ldc.i4.s 0xF
0x12586  box      [mscorlib]System.Int32
0x1258b  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x12590  br.s     loc_125AE
0x12592  ldloc.3
0x12593  ldarg.0
0x12594  ldloc.2
0x12595  callvirt instance object [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0x1259a  isinst   [mscorlib]System.String
0x1259f  call     instance int32 Microsoft.Crm.Service.Application.Pages.SM.Services.ServerEntityPage::ParseGranularity(string IcalString)
0x125a4  box      [mscorlib]System.Int32
0x125a9  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x125ae  ldarg.2
0x125af  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x125b4  ldstr    aAnchoroffset// "anchoroffset"
0x125b9  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x125be  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl
0x125c3  stloc.s  4
0x125c5  ldarg.2
0x125c6  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x125cb  ldstr    aDisplayanchoro// "displayanchoroffset"
0x125d0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x125d5  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl
0x125da  stloc.s  5
0x125dc  ldloc.s  4
0x125de  brfalse.s loc_12635
0x125e0  ldloc.s  5
0x125e2  brfalse.s loc_12635
0x125e4  ldloc.s  5
0x125e6  ldstr    aTime// "time"
0x125eb  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_DisplayFormat(string)
0x125f0  ldloc.s  4
0x125f2  callvirt instance object [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0x125f7  brtrue.s loc_1260A
0x125f9  ldloc.s  4
0x125fb  ldc.i4   0x1E0
0x12600  box      [mscorlib]System.Int32
0x12605  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x1260a  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x1260f  stloc.s  8
0x12611  ldloca.s 8
0x12613  ldloc.s  4
0x12615  callvirt instance object [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0x1261a  unbox.any [mscorlib]System.Int32
0x1261f  conv.r8
0x12620  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x12625  stloc.s  8
0x12627  ldloc.s  5
0x12629  ldloc.s  8
0x1262b  box      [mscorlib]System.DateTime
0x12630  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x12635  ret
```
