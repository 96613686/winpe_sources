# Microsoft.Crm.Application.WebServices.WorkflowWebService::ConvertToUTC

- ea: `0x9230`
- end: `0x924d`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::ConvertToUTC`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2d30`
- `0x3010`
- `0x41d0`

## pseudocode

```c

```

## disassembly

```asm
0x9230  ldarg.1
0x9231  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9236  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x923b  stloc.0
0x923c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x9241  callvirt instance class [mscorlib]System.TimeZone [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TimeZone()
0x9246  ldloc.0
0x9247  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZone::ToUniversalTime(valuetype [mscorlib]System.DateTime)
0x924c  ret
```
