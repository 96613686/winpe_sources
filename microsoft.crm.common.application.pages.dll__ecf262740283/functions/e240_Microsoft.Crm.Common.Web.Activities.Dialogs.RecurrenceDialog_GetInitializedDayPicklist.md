# Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedDayPicklist

- ea: `0xe240`
- end: `0xe31b`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedDayPicklist`
- size: `219`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xdbc0`
- `0xdd50`

## callees

- `0xe190`
- `0xe1e0`
- `0xe240`

## pseudocode

```c

```

## disassembly

```asm
0xe240  ldc.i4.0
0xe241  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::.ctor(valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionSorting)
0xe246  stloc.0
0xe247  ldloc.0
0xe248  ldarg.0
0xe249  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe24e  ldstr    aRecurrencerule_15// "RecurrenceRule.Dialog.DayList.Day"
0xe253  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe258  ldstr    a127// "127"
0xe25d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0xe262  ldloc.0
0xe263  ldarg.0
0xe264  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe269  ldstr    aRecurrencerule_27// "RecurrenceRule.Dialog.DayList.WeekDay"
0xe26e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe273  ldarg.0
0xe274  ldflda   int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_weekDays
0xe279  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe27e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xe283  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0xe288  ldloc.0
0xe289  ldarg.0
0xe28a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe28f  ldstr    aRecurrencerule_28// "RecurrenceRule.Dialog.DayList.WeekEndda"...
0xe294  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe299  ldarg.0
0xe29a  ldflda   int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_weekEndDays
0xe29f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe2a4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xe2a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0xe2ae  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xe2b3  stloc.1
0xe2b4  ldc.i4.0
0xe2b5  stloc.2
0xe2b6  br.s     loc_E2F4
0xe2b8  ldarg.0
0xe2b9  ldarg.0
0xe2ba  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_firstDayOfWeek
0xe2bf  ldloc.2
0xe2c0  add
0xe2c1  ldc.i4.7
0xe2c2  rem
0xe2c3  call     instance valuetype [mscorlib]System.DayOfWeek Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::DayOfWeekFromInt(int32 day)
0xe2c8  stloc.3
0xe2c9  ldarg.0
0xe2ca  ldloc.3
0xe2cb  call     instance int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetDaysOfWeekMask(valuetype [mscorlib]System.DayOfWeek dayIndex)
0xe2d0  stloc.s  4
0xe2d2  ldloc.0
0xe2d3  ldloc.1
0xe2d4  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0xe2d9  ldloc.3
0xe2da  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::GetDayName(valuetype [mscorlib]System.DayOfWeek)
0xe2df  ldloca.s 4
0xe2e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe2e6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xe2eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0xe2f0  ldloc.2
0xe2f1  ldc.i4.1
0xe2f2  add
0xe2f3  stloc.2
0xe2f4  ldloc.2
0xe2f5  ldc.i4.7
0xe2f6  blt.s    loc_E2B8
0xe2f8  ldloc.0
0xe2f9  newobj   instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::.ctor(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select)
0xe2fe  dup
0xe2ff  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xe304  ldstr    aClass// "class"
0xe309  ldstr    aMsCrmSelectbox// "ms-crm-SelectBox"
0xe30e  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xe313  dup
0xe314  ldarg.1
0xe315  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xe31a  ret
```
