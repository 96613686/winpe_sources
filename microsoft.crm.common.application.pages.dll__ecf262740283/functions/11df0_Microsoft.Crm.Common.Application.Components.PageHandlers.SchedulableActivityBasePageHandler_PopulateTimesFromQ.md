# Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::PopulateTimesFromQueryString

- ea: `0x11df0`
- end: `0x11e96`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::PopulateTimesFromQueryString`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x11c00`

## callees

- `0x11510`
- `0x11b80`
- `0x11df0`

## string_xrefs

- `0x11e25`: `scheduledstart`
- `0x11e36`: `scheduledend`
- `0x11e46`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x11df0  ldarg.0
0x11df1  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11df6  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x11dfb  brfalse  loc_11E95
0x11e00  ldarg.0
0x11e01  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x11e06  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11e0b  ldstr    aStarttime// "_StartTime"
0x11e10  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11e15  stloc.0
0x11e16  ldloc.0
0x11e17  brfalse.s loc_11E95
0x11e19  ldarg.0
0x11e1a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x11e1f  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.ActivityForm
0x11e24  dup
0x11e25  ldstr    aScheduledstart// "scheduledstart"
0x11e2a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x11e2f  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl
0x11e34  stloc.1
0x11e35  dup
0x11e36  ldstr    aScheduledend// "scheduledend"
0x11e3b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x11e40  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl
0x11e45  stloc.2
0x11e46  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x11e4b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x11e50  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DurationControl
0x11e55  ldloc.0
0x11e56  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm]Microsoft.Crm.CrmCalendarUtil::IsoDateTimeStringToDateTime(string)
0x11e5b  stloc.3
0x11e5c  ldloc.1
0x11e5d  ldloc.3
0x11e5e  box      [mscorlib]System.DateTime
0x11e63  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x11e68  ldloc.2
0x11e69  ldloc.3
0x11e6a  ldarg.0
0x11e6b  ldfld    int32 Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::_minutesPerInterval
0x11e70  conv.r8
0x11e71  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x11e76  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x11e7b  box      [mscorlib]System.DateTime
0x11e80  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x11e85  ldarg.0
0x11e86  call     instance int32 Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::get_MinutesPerInterval()
0x11e8b  box      [mscorlib]System.Int32
0x11e90  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x11e95  ret
```
