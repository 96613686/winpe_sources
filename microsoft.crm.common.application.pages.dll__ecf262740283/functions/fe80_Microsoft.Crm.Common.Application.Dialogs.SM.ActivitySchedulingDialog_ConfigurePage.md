# Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::ConfigurePage

- ea: `0xfe80`
- end: `0x1022e`
- name: `Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::ConfigurePage`
- size: `942`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xfd80`
- `0xfd90`
- `0xfda0`
- `0xfdf0`
- `0x10230`

## string_xrefs

- `0xfee8`: `/_common/styles/miniCal.css.aspx`
- `0xfef8`: `/_static/_common/styles/AutoToolTip.js`
- `0x10158`: `serviceid_c`

## pseudocode

```c

```

## disassembly

```asm
0xfe80  ldarg.0
0xfe81  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigurePage()
0xfe86  ldarg.0
0xfe87  ldarg.0
0xfe88  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::get_ActivityType()
0xfe8d  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xfe92  ldarg.0
0xfe93  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfe98  ldstr    aStaticSmActivi// "/_static/sm/activityscheduling/scheduli"...
0xfe9d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xfea2  ldarg.0
0xfea3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfea8  ldstr    aStaticSmActivi_0// "/_static/sm/activityscheduling/activity"...
0xfead  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xfeb2  ldarg.0
0xfeb3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfeb8  ldstr    aStaticControls// "/_static/_controls/lookup/lookup.js"
0xfebd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xfec2  ldarg.0
0xfec3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfec8  ldstr    aStaticControls_10// "/_static/_controls/datetime/time.js"
0xfecd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xfed2  ldarg.0
0xfed3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfed8  ldstr    aStaticControls_0// "/_static/_controls/datetime/date.js"
0xfedd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xfee2  ldarg.0
0xfee3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfee8  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0xfeed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xfef2  ldarg.0
0xfef3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfef8  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0xfefd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff02  ldarg.0
0xff03  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff08  ldstr    aSnewcontextfro// "_sNewContextFromFocus"
0xff0d  ldstr    asc_1F1DE// ""
0xff12  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xff17  ldarg.0
0xff18  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff1d  ldstr    aSactivityid// "_sActivityId"
0xff22  ldarg.0
0xff23  call     instance string Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::get_ActivityId()
0xff28  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xff2d  ldarg.0
0xff2e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff33  ldstr    aIrecordsperpag// "_iRecordsPerPage"
0xff38  ldarg.0
0xff39  call     instance int32 Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::get_RecordsPerPage()
0xff3e  conv.i8
0xff3f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xff44  ldarg.0
0xff45  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff4a  ldstr    aSusertimezonec// "_sUserTimeZoneCode"
0xff4f  ldarg.0
0xff50  call     instance int32 Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::get_UserTimeZoneCode()
0xff55  stloc.1
0xff56  ldloca.s 1
0xff58  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xff5d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xff62  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xff67  ldarg.0
0xff68  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff6d  ldstr    aBautosearch// "_bAutoSearch"
0xff72  ldarg.0
0xff73  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xff78  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xff7d  ldstr    aAutosearch// "autoSearch"
0xff82  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xff87  ldstr    aTrue// "true"
0xff8c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xff91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xff96  ldarg.0
0xff97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xff9c  ldstr    aSasap// "_sASAP"
0xffa1  ldc.i4.1
0xffa2  stloc.2
0xffa3  ldloca.s 2
0xffa5  constrained. Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0xffab  callvirt instance string [mscorlib]System.Object::ToString()
0xffb0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xffb5  ldarg.0
0xffb6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xffbb  ldstr    aSspecificdate// "_sSpecificDate"
0xffc0  ldc.i4.2
0xffc1  stloc.2
0xffc2  ldloca.s 2
0xffc4  constrained. Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0xffca  callvirt instance string [mscorlib]System.Object::ToString()
0xffcf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xffd4  ldarg.0
0xffd5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xffda  ldstr    aSrangeofdates// "_sRangeOfDates"
0xffdf  ldc.i4.3
0xffe0  stloc.2
0xffe1  ldloca.s 2
0xffe3  constrained. Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0xffe9  callvirt instance string [mscorlib]System.Object::ToString()
0xffee  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xfff3  ldarg.0
0xfff4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfff9  ldstr    aStoday// "_sToday"
0xfffe  ldc.i4.4
0xffff  stloc.2
0x10000  ldloca.s 2
0x10002  constrained. Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x10008  callvirt instance string [mscorlib]System.Object::ToString()
0x1000d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x10012  ldarg.0
0x10013  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10018  ldstr    aStomorrow// "_sTomorrow"
0x1001d  ldc.i4.5
0x1001e  stloc.2
0x1001f  ldloca.s 2
0x10021  constrained. Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x10027  callvirt instance string [mscorlib]System.Object::ToString()
0x1002c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x10031  ldarg.0
0x10032  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10037  ldstr    aSthisweek// "_sThisWeek"
0x1003c  ldc.i4.6
0x1003d  stloc.2
0x1003e  ldloca.s 2
0x10040  constrained. Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x10046  callvirt instance string [mscorlib]System.Object::ToString()
0x1004b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x10050  ldarg.0
0x10051  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10056  ldstr    aSnextweek// "_sNextWeek"
0x1005b  ldc.i4.7
0x1005c  stloc.2
0x1005d  ldloca.s 2
0x1005f  constrained. Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x10065  callvirt instance string [mscorlib]System.Object::ToString()
0x1006a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1006f  ldarg.0
0x10070  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10075  ldstr    aSnextmonth// "_sNextMonth"
0x1007a  ldc.i4.8
0x1007b  stloc.2
0x1007c  ldloca.s 2
0x1007e  constrained. Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x10084  callvirt instance string [mscorlib]System.Object::ToString()
0x10089  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1008e  ldarg.0
0x1008f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10094  ldstr    aSanytime// "_sAnyTime"
0x10099  ldc.i4.s 0x20
0x1009b  stloc.1
0x1009c  ldloca.s 1
0x1009e  ldstr    aD// "D"
0x100a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x100a8  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x100ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x100b2  ldarg.0
0x100b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x100b8  ldstr    aSspecifictime// "_sSpecificTime"
0x100bd  ldc.i4.s 0x21
0x100bf  stloc.3
0x100c0  ldloca.s 3
0x100c2  constrained. Microsoft.Crm.Common.Application.Dialogs.SM.StartTimeCategory
0x100c8  callvirt instance string [mscorlib]System.Object::ToString()
0x100cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x100d2  ldarg.0
0x100d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x100d8  ldstr    aSrangeoftimes// "_sRangeOfTimes"
0x100dd  ldc.i4.s 0x22
0x100df  stloc.3
0x100e0  ldloca.s 3
0x100e2  constrained. Microsoft.Crm.Common.Application.Dialogs.SM.StartTimeCategory
0x100e8  callvirt instance string [mscorlib]System.Object::ToString()
0x100ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x100f2  ldarg.0
0x100f3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x100f8  ldstr    aSmorning// "_sMorning"
0x100fd  ldc.i4.1
0x100fe  stloc.1
0x100ff  ldloca.s 1
0x10101  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10106  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1010b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x10110  ldarg.0
0x10111  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10116  ldstr    aSafternoon// "_sAfternoon"
0x1011b  ldc.i4.2
0x1011c  stloc.1
0x1011d  ldloca.s 1
0x1011f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10124  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x10129  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1012e  ldarg.0
0x1012f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10134  ldstr    aSevening// "_sEvening"
0x10139  ldc.i4.3
0x1013a  stloc.1
0x1013b  ldloca.s 1
0x1013d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10142  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x10147  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1014c  ldarg.0
0x1014d  ldstr    aCustomersC// "customers_c"
0x10152  call     instance void Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::AddAutoToolTipControl(string elementId)
0x10157  ldarg.0
0x10158  ldstr    aServiceidC// "serviceid_c"
0x1015d  call     instance void Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::AddAutoToolTipControl(string elementId)
0x10162  ldarg.0
0x10163  ldstr    aResourcesC// "resources_c"
0x10168  call     instance void Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::AddAutoToolTipControl(string elementId)
0x1016d  ldarg.0
0x1016e  ldstr    aSiteidC// "siteid_c"
0x10173  call     instance void Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::AddAutoToolTipControl(string elementId)
0x10178  ldarg.0
0x10179  ldstr    aSearchstartdat// "SearchStartDate_c"
0x1017e  call     instance void Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::AddAutoToolTipControl(string elementId)
0x10183  ldarg.0
0x10184  ldstr    aSearchstarttim// "SearchStartTime_c"
0x10189  call     instance void Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::AddAutoToolTipControl(string elementId)
0x1018e  ldarg.0
0x1018f  ldstr    aDurationC// "duration_c"
0x10194  call     instance void Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::AddAutoToolTipControl(string elementId)
0x10199  ldarg.0
0x1019a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::get_ActivityType()
0x1019f  ldc.i4.1
0x101a0  ldnull
0x101a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x101a6  stloc.0
0x101a7  ldarg.0
0x101a8  ldarg.0
0x101a9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x101ae  ldstr    aSmActivitySche// "SM_Activity_Scheduling_Dialog_Title"
0x101b3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x101b8  ldc.i4.1
0x101b9  newarr   [mscorlib]System.Object
0x101be  dup
0x101bf  ldc.i4.0
0x101c0  ldloc.0
0x101c1  stelem.ref
0x101c2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x101c7  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x101cc  ldarg.0
0x101cd  ldarg.0
0x101ce  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x101d3  ldstr    aSmActivitySche_0// "SM_Activity_Scheduling_Dialog_Descripti"...
0x101d8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x101dd  ldc.i4.1
0x101de  newarr   [mscorlib]System.Object
0x101e3  dup
0x101e4  ldc.i4.0
0x101e5  ldloc.0
0x101e6  stelem.ref
0x101e7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x101ec  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x101f1  ldarg.0
0x101f2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x101f7  ldc.i4.s 0x10
0x101f9  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x101fe  pop
0x101ff  ldarg.0
0x10200  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x10205  ldstr    aBookbutton// "BookButton"
0x1020a  ldstr    aButtonLabelSel// "Button_Label_Select_Proposal"
0x1020f  ldstr    aSelectproposal// "SelectProposal();"
0x10214  ldc.i4.1
0x10215  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0x1021a  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0x1021f  pop
0x10220  ldarg.0
0x10221  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x10226  ldc.i4.2
0x10227  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x1022c  pop
0x1022d  ret
```
