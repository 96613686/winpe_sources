# Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::ConfigurePage

- ea: `0x13f70`
- end: `0x14255`
- name: `Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::ConfigurePage`
- size: `741`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x13f70`

## string_xrefs

- `0x13f7d`: `readonly`
- `0x13f99`: `readonly`

## pseudocode

```c

```

## disassembly

```asm
0x13f70  ldc.i4.0
0x13f71  stloc.0
0x13f72  ldarg.0
0x13f73  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13f78  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x13f7d  ldstr    aReadonly// "readonly"
0x13f82  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13f87  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13f8c  brtrue.s loc_13FAE
0x13f8e  ldarg.0
0x13f8f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13f94  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x13f99  ldstr    aReadonly// "readonly"
0x13f9e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13fa3  ldstr    a1// "1"
0x13fa8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13fad  stloc.0
0x13fae  ldarg.0
0x13faf  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayduration
0x13fb4  ldarg.0
0x13fb5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13fba  ldstr    aAppdurationcon// "AppDurationControl_Minute"
0x13fbf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13fc4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_MinuteFormatString(string)
0x13fc9  ldarg.0
0x13fca  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayduration
0x13fcf  ldarg.0
0x13fd0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13fd5  ldstr    aAppdurationcon_0// "AppDurationControl_Minutes"
0x13fda  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13fdf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_MinutesFormatString(string)
0x13fe4  ldarg.0
0x13fe5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayduration
0x13fea  ldarg.0
0x13feb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13ff0  ldstr    aAppdurationcon_1// "AppDurationControl_Hour"
0x13ff5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13ffa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_HourFormatString(string)
0x13fff  ldarg.0
0x14000  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayduration
0x14005  ldarg.0
0x14006  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1400b  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0x14010  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14015  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_HoursFormatString(string)
0x1401a  ldarg.0
0x1401b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayduration
0x14020  ldarg.0
0x14021  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x14026  ldstr    aAppdurationcon_3// "AppDurationControl_Day"
0x1402b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14030  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_DayFormatString(string)
0x14035  ldarg.0
0x14036  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayduration
0x1403b  ldarg.0
0x1403c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x14041  ldstr    aAppdurationcon_4// "AppDurationControl_Days"
0x14046  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1404b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_DaysFormatString(string)
0x14050  ldarg.0
0x14051  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayduration
0x14056  ldc.i4.2
0x14057  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::set_Required(int32)
0x1405c  ldarg.0
0x1405d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14062  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14067  ldstr    aParamduration// "paramduration"
0x1406c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14071  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x14076  brtrue.s loc_140A5
0x14078  ldarg.0
0x14079  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayduration
0x1407e  ldarg.0
0x1407f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14084  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14089  ldstr    aParamduration// "paramduration"
0x1408e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14093  ldc.i4.7
0x14094  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14099  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1409e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_Value(int32)
0x140a3  br.s     loc_140B2
0x140a5  ldarg.0
0x140a6  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayduration
0x140ab  ldc.i4.s 0x3C
0x140ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_Value(int32)
0x140b2  ldarg.0
0x140b3  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayduration
0x140b8  ldloc.0
0x140b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x140be  ldarg.0
0x140bf  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displaygranularity
0x140c4  ldarg.0
0x140c5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x140ca  ldstr    aAppdurationcon// "AppDurationControl_Minute"
0x140cf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x140d4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_MinuteFormatString(string)
0x140d9  ldarg.0
0x140da  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displaygranularity
0x140df  ldarg.0
0x140e0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x140e5  ldstr    aAppdurationcon_0// "AppDurationControl_Minutes"
0x140ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x140ef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_MinutesFormatString(string)
0x140f4  ldarg.0
0x140f5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displaygranularity
0x140fa  ldarg.0
0x140fb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x14100  ldstr    aAppdurationcon_1// "AppDurationControl_Hour"
0x14105  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1410a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_HourFormatString(string)
0x1410f  ldarg.0
0x14110  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displaygranularity
0x14115  ldarg.0
0x14116  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1411b  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0x14120  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14125  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_HoursFormatString(string)
0x1412a  ldarg.0
0x1412b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displaygranularity
0x14130  ldarg.0
0x14131  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x14136  ldstr    aAppdurationcon_3// "AppDurationControl_Day"
0x1413b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14140  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_DayFormatString(string)
0x14145  ldarg.0
0x14146  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displaygranularity
0x1414b  ldarg.0
0x1414c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x14151  ldstr    aAppdurationcon_4// "AppDurationControl_Days"
0x14156  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1415b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_DaysFormatString(string)
0x14160  ldarg.0
0x14161  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displaygranularity
0x14166  ldc.i4.2
0x14167  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::set_Required(int32)
0x1416c  ldarg.0
0x1416d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14172  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14177  ldstr    aParamgranulari// "paramgranularity"
0x1417c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14181  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x14186  brtrue.s loc_141B5
0x14188  ldarg.0
0x14189  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displaygranularity
0x1418e  ldarg.0
0x1418f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14194  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14199  ldstr    aParamgranulari// "paramgranularity"
0x1419e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x141a3  ldc.i4.7
0x141a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x141a9  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x141ae  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_Value(int32)
0x141b3  br.s     loc_141C2
0x141b5  ldarg.0
0x141b6  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displaygranularity
0x141bb  ldc.i4.s 0xF
0x141bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_Value(int32)
0x141c2  ldarg.0
0x141c3  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displaygranularity
0x141c8  ldloc.0
0x141c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x141ce  ldarg.0
0x141cf  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayanchoroffset
0x141d4  ldstr    aTime// "time"
0x141d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0x141de  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x141e3  stloc.1
0x141e4  ldarg.0
0x141e5  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x141ea  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x141ef  ldstr    aParamanchoroff// "paramanchoroffset"
0x141f4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x141f9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x141fe  brtrue.s loc_1422B
0x14200  ldloca.s 1
0x14202  ldarg.0
0x14203  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14208  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1420d  ldstr    aParamanchoroff// "paramanchoroffset"
0x14212  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14217  ldc.i4.7
0x14218  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1421d  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x14222  conv.r8
0x14223  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x14228  stloc.1
0x14229  br.s     loc_1423C
0x1422b  ldloca.s 1
0x1422d  ldc.r8   480.0
0x14236  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x1423b  stloc.1
0x1423c  ldarg.0
0x1423d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayanchoroffset
0x14242  ldloc.1
0x14243  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0x14248  ldarg.0
0x14249  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Pages.SM.resourcespecs.SchedulingPage::displayanchoroffset
0x1424e  ldloc.0
0x1424f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x14254  ret
```
