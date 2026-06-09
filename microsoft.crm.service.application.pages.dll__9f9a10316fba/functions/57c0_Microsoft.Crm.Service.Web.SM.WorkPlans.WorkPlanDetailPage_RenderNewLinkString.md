# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderNewLinkString

- ea: `0x57c0`
- end: `0x58d2`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderNewLinkString`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5700`

## callees

- `0x4300`

## pseudocode

```c

```

## disassembly

```asm
0x57c0  ldarg.0
0x57c1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x57c6  ldstr    aSmWeeklySchedu// "SM_Weekly_Schedule"
0x57cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x57d0  stloc.0
0x57d1  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x57d6  ldarg.0
0x57d7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x57dc  ldstr    aMenuitemToolti// "MenuItem_ToolTip_NewObject"
0x57e1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x57e6  ldc.i4.1
0x57e7  newarr   [mscorlib]System.Object
0x57ec  dup
0x57ed  ldc.i4.0
0x57ee  ldloc.0
0x57ef  stelem.ref
0x57f0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x57f5  stloc.0
0x57f6  ldstr    aSmWorkplansEdi// "/SM/workplans/edit.aspx"
0x57fb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5800  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5805  stloc.1
0x5806  ldloc.1
0x5807  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x580c  ldstr    aId// "id"
0x5811  ldstr    asc_15D82// ""
0x5816  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x581b  ldloc.1
0x581c  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x5821  ldstr    aCalendarid// "calendarId"
0x5826  ldarg.0
0x5827  call     instance string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::get_CalendarId()
0x582c  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5831  ldloc.1
0x5832  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x5837  ldstr    aResourceid_0// "resourceid"
0x583c  ldarga.s 1
0x583e  ldstr    aB// "B"
0x5843  call     instance string [mscorlib]System.Guid::ToString(string)
0x5848  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x584d  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x5852  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5857  ldloc.1
0x5858  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x585d  ldstr    aOtype// "oType"
0x5862  ldarg.0
0x5863  ldfld    string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_parentType
0x5868  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x586d  ldloc.1
0x586e  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x5873  ldstr    aName// "name"
0x5878  ldstr    aWorkingHours// "Working Hours"
0x587d  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5882  ldloc.1
0x5883  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x5888  ldstr    aMode// "mode"
0x588d  ldstr    aNew_0// "New"
0x5892  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5897  ldc.i4.5
0x5898  newarr   [mscorlib]System.String
0x589d  dup
0x589e  ldc.i4.0
0x589f  ldstr    aAHref// "<a href=\""
0x58a4  stelem.ref
0x58a5  dup
0x58a6  ldc.i4.1
0x58a7  ldloc.1
0x58a8  callvirt instance string [mscorlib]System.Object::ToString()
0x58ad  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x58b2  stelem.ref
0x58b3  dup
0x58b4  ldc.i4.2
0x58b5  ldstr    asc_1B304// "\">"
0x58ba  stelem.ref
0x58bb  dup
0x58bc  ldc.i4.3
0x58bd  ldloc.0
0x58be  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x58c3  stelem.ref
0x58c4  dup
0x58c5  ldc.i4.4
0x58c6  ldstr    aA// "</a>"
0x58cb  stelem.ref
0x58cc  call     string [mscorlib]System.String::Concat(string[])
0x58d1  ret
```
