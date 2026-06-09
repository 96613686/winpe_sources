# Microsoft.Crm.Service.Application.Components.PageHandlers.CalendarEntityPageHandler::Initialize

- ea: `0xce50`
- end: `0xcf4c`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.CalendarEntityPageHandler::Initialize`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xce50`

## pseudocode

```c

```

## disassembly

```asm
0xce50  ldarg.0
0xce51  ldstr    aCalendar// "calendar"
0xce56  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xce5b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xce60  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xce65  ldarg.0
0xce66  ldarg.1
0xce67  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::Initialize(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager)
0xce6c  ldarg.0
0xce6d  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_Request()
0xce72  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequest::get_Cookies()
0xce77  ldstr    aCalendar// "calendar"
0xce7c  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::Get(string)
0xce81  stloc.0
0xce82  ldarg.0
0xce83  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_Request()
0xce88  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xce8d  ldstr    aOid// "oId"
0xce92  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xce97  brfalse.s loc_CEC9
0xce99  ldarg.0
0xce9a  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_Request()
0xce9f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xcea4  ldstr    aOid// "oId"
0xcea9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xceae  callvirt instance string [mscorlib]System.Object::ToString()
0xceb3  ldc.i4.2
0xceb4  stloc.1
0xceb5  ldloca.s 1
0xceb7  constrained. [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ServiceCalendarType
0xcebd  callvirt instance string [mscorlib]System.Object::ToString()
0xcec2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcec7  brtrue.s loc_CEE8
0xcec9  ldloc.0
0xceca  brfalse.s loc_CF32
0xcecc  ldloc.0
0xcecd  callvirt instance string [System.Web]System.Web.HttpCookie::get_Value()
0xced2  ldc.i4.2
0xced3  stloc.1
0xced4  ldloca.s 1
0xced6  constrained. [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ServiceCalendarType
0xcedc  callvirt instance string [mscorlib]System.Object::ToString()
0xcee1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcee6  brfalse.s loc_CF32
0xcee8  ldarg.0
0xcee9  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppViewSelectorLite [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_ViewSelector()
0xceee  ldc.i4.1
0xceef  newarr   [mscorlib]System.String
0xcef4  dup
0xcef5  ldc.i4.0
0xcef6  ldstr    a06453a1d92884f// "06453a1d-9288-4f0e-9351-819d619ecb5f"
0xcefb  stelem.ref
0xcefc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppViewSelector::SetViewIds(string[])
0xcf01  ldloc.0
0xcf02  brfalse.s loc_CF4B
0xcf04  ldloc.0
0xcf05  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xcf0a  stloc.2
0xcf0b  ldloca.s 2
0xcf0d  ldc.r8   -1.0
0xcf16  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xcf1b  callvirt instance void [System.Web]System.Web.HttpCookie::set_Expires(valuetype [mscorlib]System.DateTime)
0xcf20  ldarg.1
0xcf21  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xcf26  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpResponse::get_Cookies()
0xcf2b  ldloc.0
0xcf2c  callvirt instance void [System.Web]System.Web.HttpCookieCollection::Add(class [System.Web]System.Web.HttpCookie)
0xcf31  ret
0xcf32  ldarg.0
0xcf33  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppViewSelectorLite [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_ViewSelector()
0xcf38  ldc.i4.1
0xcf39  newarr   [mscorlib]System.String
0xcf3e  dup
0xcf3f  ldc.i4.0
0xcf40  ldstr    aF4d446e037494b// "f4d446e0-3749-4ba4-9c85-eab861eafdfc"
0xcf45  stelem.ref
0xcf46  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppViewSelector::SetViewIds(string[])
0xcf4b  ret
```
