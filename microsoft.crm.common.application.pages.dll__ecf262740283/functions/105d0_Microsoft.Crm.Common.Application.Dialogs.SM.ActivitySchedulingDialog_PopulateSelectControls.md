# Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::PopulateSelectControls

- ea: `0x105d0`
- end: `0x10a96`
- name: `Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::PopulateSelectControls`
- size: `1222`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10250`

## callees

- `0x105d0`

## string_xrefs

- `0x1066d`: `Search.Date.Range.CommonDates`
- `0x107cc`: `Search.Time.Range.CommonTimes`

## pseudocode

```c

```

## disassembly

```asm
0x105d0  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0x105d5  stloc.0
0x105d6  ldarg.0
0x105d7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchStartDate
0x105dc  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::.ctor()
0x105e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddOptionGroup(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup)
0x105e6  ldarg.0
0x105e7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchStartDate
0x105ec  ldarg.0
0x105ed  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x105f2  ldstr    aSearchDateStar// "Search.Date.Start.ASAP"
0x105f7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x105fc  ldc.i4.1
0x105fd  box      Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x10602  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10607  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x1060c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x10611  ldarg.0
0x10612  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchStartDate
0x10617  ldarg.0
0x10618  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1061d  ldstr    aSearchDateStar_0// "Search.Date.Start.SpecificDate"
0x10622  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10627  ldc.i4.2
0x10628  box      Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x1062d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10632  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x10637  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x1063c  ldarg.0
0x1063d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchStartDate
0x10642  ldarg.0
0x10643  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10648  ldstr    aSearchDateStar_1// "Search.Date.Start.RangeOfDates"
0x1064d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10652  ldc.i4.3
0x10653  box      Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x10658  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1065d  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x10662  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x10667  ldarg.0
0x10668  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1066d  ldstr    aSearchDateRang// "Search.Date.Range.CommonDates"
0x10672  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10677  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::.ctor(string)
0x1067c  stloc.1
0x1067d  ldloc.1
0x1067e  ldarg.0
0x1067f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10684  ldstr    aSearchDateRang_0// "Search.Date.Range.Today"
0x10689  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1068e  ldc.i4.4
0x1068f  box      Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x10694  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10699  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x1069e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x106a3  ldloc.1
0x106a4  ldarg.0
0x106a5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x106aa  ldstr    aSearchDateRang_1// "Search.Date.Range.Tomorrow"
0x106af  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x106b4  ldc.i4.5
0x106b5  box      Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x106ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x106bf  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x106c4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x106c9  ldloc.1
0x106ca  ldarg.0
0x106cb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x106d0  ldstr    aSearchDateRang_2// "Search.Date.Range.ThisWeek"
0x106d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x106da  ldc.i4.6
0x106db  box      Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x106e0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x106e5  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x106ea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x106ef  ldloc.1
0x106f0  ldarg.0
0x106f1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x106f6  ldstr    aSearchDateRang_3// "Search.Date.Range.NextWeek"
0x106fb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10700  ldc.i4.7
0x10701  box      Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x10706  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1070b  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x10710  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x10715  ldloc.1
0x10716  ldarg.0
0x10717  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1071c  ldstr    aSearchDateRang_4// "Search.Date.Range.NextMonth"
0x10721  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10726  ldc.i4.8
0x10727  box      Microsoft.Crm.Common.Application.Dialogs.SM.StartDateCategory
0x1072c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10731  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x10736  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x1073b  ldarg.0
0x1073c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchStartDate
0x10741  ldloc.1
0x10742  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddOptionGroup(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup)
0x10747  ldarg.0
0x10748  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchStartTime
0x1074d  ldarg.0
0x1074e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10753  ldstr    aSearchTimeRang// "Search.Time.Range.Anytime"
0x10758  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1075d  ldc.i4.s 0x20
0x1075f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10764  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x10769  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x1076e  ldarg.0
0x1076f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchStartTime
0x10774  ldarg.0
0x10775  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1077a  ldstr    aSearchTimeRang_0// "Search.Time.Range.SpecificTime"
0x1077f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10784  ldc.i4.s 0x21
0x10786  box      Microsoft.Crm.Common.Application.Dialogs.SM.StartTimeCategory
0x1078b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10790  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x10795  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x1079a  ldarg.0
0x1079b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchStartTime
0x107a0  ldarg.0
0x107a1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x107a6  ldstr    aSearchTimeRang_1// "Search.Time.Range.RangeOfTimes"
0x107ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x107b0  ldc.i4.s 0x22
0x107b2  box      Microsoft.Crm.Common.Application.Dialogs.SM.StartTimeCategory
0x107b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x107bc  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x107c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x107c6  ldarg.0
0x107c7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x107cc  ldstr    aSearchTimeRang_2// "Search.Time.Range.CommonTimes"
0x107d1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x107d6  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::.ctor(string)
0x107db  stloc.2
0x107dc  ldloc.2
0x107dd  ldarg.0
0x107de  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x107e3  ldstr    aSearchTimeRang_3// "Search.Time.Range.Morning"
0x107e8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x107ed  ldc.i4.1
0x107ee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x107f3  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x107f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x107fd  ldloc.2
0x107fe  ldarg.0
0x107ff  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10804  ldstr    aSearchTimeRang_4// "Search.Time.Range.Afternoon"
0x10809  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1080e  ldc.i4.2
0x1080f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10814  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x10819  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x1081e  ldloc.2
0x1081f  ldarg.0
0x10820  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10825  ldstr    aSearchTimeRang_5// "Search.Time.Range.Evening"
0x1082a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1082f  ldc.i4.3
0x10830  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10835  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x1083a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x1083f  ldarg.0
0x10840  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchStartTime
0x10845  ldloc.2
0x10846  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddOptionGroup(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup)
0x1084b  ldarg.0
0x1084c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchStartTime
0x10851  ldc.i4.s 0x22
0x10853  stloc.s  8
0x10855  ldloca.s 8
0x10857  constrained. Microsoft.Crm.Common.Application.Dialogs.SM.StartTimeCategory
0x1085d  callvirt instance string [mscorlib]System.Object::ToString()
0x10862  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x10867  ldarg.0
0x10868  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchSpecificDate
0x1086d  ldloca.s 0
0x1086f  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x10874  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0x10879  ldarg.0
0x1087a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchDateBefore
0x1087f  ldloca.s 0
0x10881  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x10886  stloc.s  9
0x10888  ldloca.s 9
0x1088a  ldc.r8   7.0
0x10893  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x10898  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0x1089d  ldarg.0
0x1089e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchDateAfter
0x108a3  ldloca.s 0
0x108a5  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x108aa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0x108af  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x108b4  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x108b9  callvirt instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.Globalization.DateTimeFormatInfo::get_FirstDayOfWeek()
0x108be  stloc.3
0x108bf  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x108c4  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x108c9  callvirt instance string[] [mscorlib]System.Globalization.DateTimeFormatInfo::get_DayNames()
0x108ce  stloc.s  4
0x108d0  ldarg.0
0x108d1  ldloc.s  4
0x108d3  ldloc.3
0x108d4  ldc.i4.7
0x108d5  rem
0x108d6  ldelem.ref
0x108d7  stfld    string Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::DayOfWeekName0
0x108dc  ldarg.0
0x108dd  ldloc.s  4
0x108df  ldloc.3
0x108e0  ldc.i4.1
0x108e1  add
0x108e2  ldc.i4.7
0x108e3  rem
0x108e4  ldelem.ref
0x108e5  stfld    string Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::DayOfWeekName1
0x108ea  ldarg.0
0x108eb  ldloc.s  4
0x108ed  ldloc.3
0x108ee  ldc.i4.2
0x108ef  add
0x108f0  ldc.i4.7
0x108f1  rem
0x108f2  ldelem.ref
0x108f3  stfld    string Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::DayOfWeekName2
0x108f8  ldarg.0
0x108f9  ldloc.s  4
0x108fb  ldloc.3
0x108fc  ldc.i4.3
0x108fd  add
0x108fe  ldc.i4.7
0x108ff  rem
0x10900  ldelem.ref
0x10901  stfld    string Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::DayOfWeekName3
0x10906  ldarg.0
0x10907  ldloc.s  4
0x10909  ldloc.3
0x1090a  ldc.i4.4
0x1090b  add
0x1090c  ldc.i4.7
0x1090d  rem
0x1090e  ldelem.ref
0x1090f  stfld    string Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::DayOfWeekName4
0x10914  ldarg.0
0x10915  ldloc.s  4
0x10917  ldloc.3
0x10918  ldc.i4.5
0x10919  add
0x1091a  ldc.i4.7
0x1091b  rem
0x1091c  ldelem.ref
0x1091d  stfld    string Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::DayOfWeekName5
0x10922  ldarg.0
0x10923  ldloc.s  4
0x10925  ldloc.3
0x10926  ldc.i4.6
0x10927  add
0x10928  ldc.i4.7
0x10929  rem
0x1092a  ldelem.ref
0x1092b  stfld    string Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::DayOfWeekName6
0x10930  ldarg.0
0x10931  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::DayOfWeek0
0x10936  ldloc.3
0x10937  ldc.i4.7
0x10938  rem
0x10939  stloc.s  0xA
0x1093b  ldloca.s 0xA
0x1093d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10942  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x10947  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x1094c  ldarg.0
0x1094d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::DayOfWeek1
0x10952  ldloc.3
0x10953  ldc.i4.1
0x10954  add
0x10955  ldc.i4.7
0x10956  rem
0x10957  stloc.s  0xA
0x10959  ldloca.s 0xA
0x1095b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10960  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x10965  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x1096a  ldarg.0
0x1096b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::DayOfWeek2
0x10970  ldloc.3
0x10971  ldc.i4.2
0x10972  add
0x10973  ldc.i4.7
0x10974  rem
0x10975  stloc.s  0xA
0x10977  ldloca.s 0xA
0x10979  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1097e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x10983  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x10988  ldarg.0
0x10989  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::DayOfWeek3
  ... truncated ...
```
